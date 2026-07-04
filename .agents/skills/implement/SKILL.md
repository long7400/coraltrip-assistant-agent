---
name: implement
description: "Implement a piece of work based on a PRD or set of issues."
---

Implement the work described by the user in the PRD or issues.

Prefer one approved issue at a time. If the user passes a PRD plus issues, pick only the selected issue; if no issue is selected and the PRD is large, stop and ask for the target slice.

Before editing:

1. Read the parent PRD/spec, selected issue, linked research/prototype verdicts, `CONTEXT.md`, relevant ADRs, and `docs/agents/matt-skill-workflow.md`.
2. Restate the issue claim, acceptance criteria, verification plan, and any mechanism the claim requires.
3. If the requested outcome requires mechanism X, do not implement adjacent mechanism Y unless the user explicitly accepts the reduced claim.
4. Identify the repo's existing feedback loops and prefer those over invented checks. If the issue depends on missing AX setup, surface that before broad implementation.

Use `$tdd` where possible, at pre-agreed seams. Work in vertical red-green slices, not horizontal layers.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use `$code-review` to review the work against both the source spec and repo standards. If the current surface cannot run sub-agents, say so and ask whether the user wants a local two-axis review in the main context instead.

Do not create a git commit unless the user explicitly asks for one. If no commit was requested, finish with the verification evidence and a concise suggested commit message.
