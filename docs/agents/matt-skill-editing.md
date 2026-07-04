# Matt Skill Editing Contract

Use this when creating, pruning, or repairing Matt Pocock skills in this repo. The goal is lower context load without changing the course workflow.

## Evidence Order

1. User instruction in the active thread.
2. Existing skill behavior and linked reference files.
3. `docs/agents/matt-skills-evaluation.md` and the referenced lesson files under `/Users/long7400/Learn/AI/All Lessons/`.
4. `$skill-creator` and `$writing-great-skills`.
5. Current official Codex/OpenAI guidance for skills, AGENTS.md, and prompting.

If these disagree, preserve the user command and the skill's current claim, then stop and ask before changing workflow logic.

## Rewrite Rules

- **Preserve workflow**: do not change trigger, required inputs, outputs, state updates, stop/ask gates, validation, or downstream artifacts while merely pruning.
- **Shrink always-loaded text first**: frontmatter `description` is the highest-leverage target. Keep the leading word and one trigger per real branch; cut restated identity prose.
- **Keep `SKILL.md` procedural**: ordered steps and checkable completion criteria stay in the skill body.
- **Disclose reference**: examples, templates, long vocabularies, and branch-only details belong in linked files with explicit "read this when..." pointers.
- **Keep one source of truth**: if a rule is in a workflow doc or reference file, point to it instead of restating it in every skill.
- **Prefer course leading words**: grill, tracer bullet, tight loop, red, seam, AX, HITL, AFK. Use the word instead of repeating its definition.
- **Delete no-ops**: remove sentences that do not change behavior compared with a normal competent Codex run.

## Prompt Discipline For Skills

- State the task, constraints, outputs, and verification in concrete terms.
- Put hard constraints before soft style guidance.
- Use imperative steps over motivational prose.
- Make failure conditions explicit: stop/ask, missing evidence, no sub-agent tooling, no red-capable loop, unresolved HITL judgement.
- Avoid stale specifics: speculative file paths, function names, class names, or generated repo maps unless accepted as current source truth.

## Validation

After edits:

1. Run `python3 /Users/long7400/.codex/skills/.system/skill-creator/scripts/quick_validate.py <skill-dir>` for every changed skill.
2. Re-run a full sweep when many descriptions or shared workflow rules changed.
3. Compare line counts and description lengths before/after when the goal is context reduction.
4. Use `rg` for stale terms, duplicated rules, and broken links.
5. Record substantive course-alignment decisions in `docs/agents/matt-skills-evaluation.md`.

## Non-Goals

- Do not copy lesson transcript prose into skills.
- Do not convert a HITL workflow into AFK work for convenience.
- Do not replace required sub-agents, primary-source research, prototype verdicts, or code-review axes with local approximations unless the user accepts the reduced claim.
- Do not commit changes unless the user explicitly asks.
