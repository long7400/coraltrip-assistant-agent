---
name: ask-matt
description: Ask which skill or flow fits your situation. A router over the skills in this repo.
---

# Ask Matt

Route the user to the smallest skill flow that preserves the requested claim. Use `docs/agents/matt-skill-workflow.md` as the project reference.

## The main flow: idea → ship

1. **`$grill-with-docs`** — sharpen the idea by interview. Start here when you **have a codebase** or any decision should persist: it's stateful, retaining what it learns in `CONTEXT.md` and ADRs. (No repo-backed docs needed? Use `$grill-me` — see Standalone. Both run the same `$grilling` primitive; `grill-with-docs` is the one that leaves a paper trail.)
2. **Branch — can you settle every question in conversation?** If a question needs primary-source facts, detour through **`$research`** and feed the result back into the main thread. If a question needs a runnable answer (state, business logic, a UI you have to see), detour through a prototype, bridged by **`$handoff`** in both directions (see Crossing sessions):
   - **`$handoff`** out, then open a fresh session against that file,
   - **`$prototype`** to answer the question with throwaway code,
   - **`$handoff`** back what you learned, and reference it from the original idea thread.
3. **Branch — is this a multi-session build?**
   - **Yes** → **`$to-prd`** (turn the thread into a PRD) → **`$to-issues`** (split the PRD into independently-grabbable issues). Because the issues are independent, **clear context between each one**: start a fresh session per issue and kick off **`$implement`** by passing it the PRD and the single issue to work on.
   - **No** → **`$implement`** right here, in the same context window.

   Either way, **`$implement`** builds each issue by driving **`$tdd`** internally — one red-green slice at a time — then closes out by running **`$code-review`**, a two-axis review (Standards + Spec) of the diff. Commit only when the user explicitly asks for a commit. Reach for **`$tdd`** on its own when you just want to build a concrete behavior test-first without a full spec, and **`$code-review`** on its own whenever you want to review a branch or PR against a fixed point.

### Context hygiene

Keep grilling -> PRD -> issues in one coherent context while it remains sharp. Use `$handoff` before degraded context; start fresh for each `$implement`.

## On-ramps

A starting situation that generates work, then merges onto the main flow.

- **Bugs and requests piling up** → **`$triage`**. It moves issues through triage roles and produces agent-ready issues, which **`$implement`** later picks up.

  Triage is only for issues **you didn't create** — bug reports, incoming feature requests, anything that arrives raw. Issues that `$to-issues` produced are already agent-ready, so **don't triage them**.

- **Something's broken** → **`$diagnosing-bugs`**. For the hard ones: the bug that resists a first glance, the intermittent flake, the regression that crept in between two known-good states. It refuses to theorise until it has a **tight feedback loop** — one command that already goes red on *this* bug — then fixes with a regression test. Its post-mortem hands off to **`$improve-codebase-architecture`** when the real finding is that there's no good seam to lock the bug down.

## Codebase health

Not feature work — upkeep.

- **`$improve-codebase-architecture`** — surface deepening opportunities. Picking one generates an idea that returns to `$grill-with-docs`.

## Vocabulary underneath

Use these directly when the words, not the process, are the problem; otherwise let the flow skills pull them in.

- **`$domain-modeling`** — sharpen the project's *domain* language: challenge a fuzzy term, resolve an overloaded word ("account" doing three jobs), record a hard-to-reverse decision as an ADR. It's the active discipline `$grill-with-docs` drives to keep `CONTEXT.md` a clean glossary.
- **`$codebase-design`** — the deep-module vocabulary (module, interface, depth, seam, adapter, leverage, locality) for designing a module's *shape*: a lot of behaviour behind a small interface at a clean seam. `$tdd` and `$improve-codebase-architecture` both speak it.

## Crossing sessions

- **`$handoff`** — write a file so a fresh session can continue with preserved context. Use when branching into/out of `$research` or `$prototype`, or when context is degrading.
- **`/compact`** — stay in the same conversation with summarized history. Use only at phase boundaries.

## Standalone

Off the main flow entirely.

- **`$grill-me`** — the same relentless interview as `$grill-with-docs`, but for when you have **no codebase**. Stateless: it saves nothing locally, builds no `CONTEXT.md`. Reach for it to sharpen any plan or design that doesn't live in a repo.
- **Greenfield setup** — if the repo is blank or only a thin skeleton, route through `$grill-with-docs` once there is a repo to write docs into, then use `$to-prd` to define Agent Experience (AX) before broad product implementation: feedback loops, technology choices, module shape, and testing strategy.
- **`$prototype`** — throwaway code answering one design question. Keep the verdict; delete or isolate the code.
- **`$research`** — sub-agent reading legwork against primary sources; wait for the cited Markdown result and feed it into PRD/issues/ADR/`CONTEXT.md`.
- Sub-agent-dependent steps (`$research`, `$code-review`, design-it-twice) require actual sub-agent tooling. If the current surface cannot create sub-agents, stop and ask before substituting a local main-context pass.
- **`$teach`** — learn a concept over multiple sessions, using the current directory as a stateful workspace.
- **`$writing-great-skills`** — reference for writing and editing skills well.

## Precondition

**`$setup-matt-pocock-skills`** — run before your first engineering flow to configure the issue tracker, triage labels, and doc layout the other skills assume. Custom issue trackers also work.
