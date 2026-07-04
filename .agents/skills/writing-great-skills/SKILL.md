---
name: writing-great-skills
description: Write or prune compact, predictable skills. Use when creating, reviewing, or reducing skill context load.
---

A skill should make the agent take the same **process** every run, not produce the same output. Keep the full vocabulary in [`GLOSSARY.md`](GLOSSARY.md); keep `SKILL.md` for the operating rules below.

If this repo has `docs/agents/matt-skill-editing.md`, read it before changing Matt skills. It records the course-alignment and context-budget contract for this project.

## Rewrite Loop

1. **Preserve the claim.** Write down the current trigger, required inputs, outputs, state changes, stop/ask gates, validation, and downstream artifact. If a rewrite would change the workflow or logic, stop unless the user asked for that change.
2. **Prune the description first.** It is the always-loaded context pointer. Front-load the leading word, keep one trigger per real branch, and keep only reach clauses such as "when another skill needs...". Delete identity prose that the body already carries.
3. **Protect the step ladder.** Keep ordered steps and checkable completion criteria in `SKILL.md`. Put branch-only reference, examples, formats, and deep vocabulary behind linked files with explicit context pointers.
4. **Hunt load.** Remove duplication, sediment, no-ops, stale details, and speculative file/function names. Collapse repeated explanations into leading words already used by the course and repo: grill, tracer bullet, tight loop, red, seam, AX, HITL, AFK.
5. **Validate behavior.** Run the skill validator, inspect description/body size, and use `rg` for stale terms. For substantial rewrites, forward-test with a realistic prompt and raw artifacts, not your intended answer.

## Split Decisions

- Split by **invocation** only when a distinct leading word should independently trigger the skill or another skill must invoke it.
- Split by **sequence** only when visible post-completion steps cause premature completion and the current step cannot get a sharper completion criterion.
- Prefer a router skill when many user-invoked procedure skills become hard to remember.

## Do Not

- Do not paste course notes into every skill. Keep course evidence in audit docs and encode only the rule that changes agent behavior.
- Do not replace a required mechanism with a nearby easier mechanism while pruning.
- Do not hide must-read instructions behind a vague pointer. If a pointer is unreliable, sharpen it before inlining.
- Do not add explanatory prose that merely praises the workflow or repeats what the model already does.
- Do not call a rewrite done until validation proves the skill is valid and the old claim is still represented.
