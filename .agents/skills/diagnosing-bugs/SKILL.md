---
name: diagnosing-bugs
description: Diagnosis loop for hard bugs and performance regressions. Use when the user says "diagnose"/"debug this", or reports something broken/throwing/failing/slow.
---

# Diagnosing Bugs

A strict diagnosis loop for hard bugs and performance regressions. Do not move from one phase to the next until its completion criterion is met.

When exploring the codebase, read `CONTEXT.md` (if it exists) to get a clear mental model of the relevant modules, and check ADRs in the area you're touching.

## Phase 1 - Build a red-capable loop

Create one command that catches the user's exact symptom. Try loop types in this order:

1. **Failing test** at whatever seam reaches the bug — unit, integration, e2e.
2. **Curl / HTTP script** against a running dev server.
3. **CLI invocation** with a fixture input, diffing stdout against a known-good snapshot.
4. **Headless browser script** (Playwright / Puppeteer) — drives the UI, asserts on DOM/console/network.
5. **Replay a captured trace.** Save a real network request / payload / event log to disk; replay it through the code path in isolation.
6. **Throwaway harness.** Spin up a minimal subset of the system (one service, mocked deps) that exercises the bug code path with a single function call.
7. **Property / fuzz loop.** If the bug is "sometimes wrong output", run 1000 random inputs and look for the failure mode.
8. **Bisection harness.** If the bug appeared between two known states (commit, dataset, version), automate "boot at state X, check, repeat" so you can `git bisect run` it.
9. **Differential loop.** Run the same input through old-version vs new-version (or two configs) and diff outputs.
10. **HITL bash script.** Last resort. If a human must click, drive _them_ with `scripts/hitl-loop.template.sh` so the loop is still structured. Captured output feeds back to you.

Tighten the loop until it is fast, deterministic, and specific: cache setup, narrow scope, pin time/RNG/filesystem/network, and assert the symptom rather than "does not crash".

For non-deterministic bugs, raise reproduction rate instead of seeking a perfect repro: loop the trigger, parallelize, add stress, narrow timing, and inject sleeps until the signal is debuggable.

If no red-capable loop can be built, stop. List attempts and ask for environment access, a captured artifact, or permission for temporary instrumentation. Do not hypothesize without a loop.

Phase 1 is done only when you have already run one named command and can paste its invocation/output. It must be:

- [ ] **Red-capable** — it drives the actual bug code path and asserts the **user's exact symptom**, so it can go red on this bug and green once fixed. Not "runs without erroring" — it must be able to _catch this specific bug_.
- [ ] **Deterministic** — same verdict every run (flaky bugs: a pinned, high reproduction rate, per above).
- [ ] **Fast** — seconds, not minutes.
- [ ] **Agent-runnable** — you can run it unattended; a human in the loop only via `scripts/hitl-loop.template.sh`.

No red-capable command, no Phase 2.

## Phase 2 - Reproduce and minimize

Run the loop. Watch it go red — the bug appears.

Confirm:

- [ ] The loop produces the failure mode the **user** described — not a different failure that happens to be nearby. Wrong bug = wrong fix.
- [ ] The failure is reproducible across multiple runs (or, for non-deterministic bugs, reproducible at a high enough rate to debug against).
- [ ] You have captured the exact symptom (error message, wrong output, slow timing) so later phases can verify the fix actually addresses it.

Shrink the repro to the smallest scenario that still goes red. Cut inputs, callers, config, data, and steps one at a time; rerun after each cut. Keep only load-bearing elements.

Done when removing any remaining element makes the loop go green.

## Phase 3 - Rank falsifiable hypotheses

Generate 3-5 ranked hypotheses before testing any. Each must state a prediction:

> If <X> is the cause, then <changing Y> will make the bug disappear / <changing Z> will make it worse.

If you cannot state the prediction, the hypothesis is a vibe — discard or sharpen it.

Show the ranked list to the user before testing. Do not block if the user is AFK.

## Phase 4 - Instrument one prediction at a time

Each probe must map to a Phase 3 prediction. Change one variable at a time.

Tool preference:

1. **Debugger / REPL inspection** if the env supports it. One breakpoint beats ten logs.
2. **Targeted logs** at the boundaries that distinguish hypotheses.
3. Never "log everything and grep".

**Tag every debug log** with a unique prefix, e.g. `[DEBUG-a4f2]`. Cleanup at the end becomes a single grep. Untagged logs survive; tagged logs die.

For performance regressions: establish a baseline measurement first (timing harness, profiler, query plan), then bisect. Measure first, fix second.

## Phase 5 - Fix and regression test

Write the regression test before the fix, but only at a correct seam: it must exercise the real bug pattern as it occurs at the call site.

If no correct seam exists, record that as the finding and flag the architecture gap for Phase 6.

If a correct seam exists:

1. Turn the minimised repro into a failing test at that seam.
2. Watch it fail.
3. Apply the fix.
4. Watch it pass.
5. Re-run the Phase 1 feedback loop against the original (un-minimised) scenario.

## Phase 6 - Cleanup and post-mortem

Required before declaring done:

- [ ] Original repro no longer reproduces (re-run the Phase 1 loop)
- [ ] Regression test passes (or absence of seam is documented)
- [ ] All `[DEBUG-...]` instrumentation removed (`grep` the prefix)
- [ ] Throwaway prototypes deleted (or moved to a clearly-marked debug location)
- [ ] The hypothesis that turned out correct is stated in the commit / PR message — so the next debugger learns

Then ask what would have prevented the bug. If the answer is architectural (no seam, tangled callers, hidden coupling), hand off to `$improve-codebase-architecture` with the concrete evidence.
