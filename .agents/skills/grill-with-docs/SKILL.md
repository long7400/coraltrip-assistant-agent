---
name: grill-with-docs
description: Repo-backed plan/design grilling with CONTEXT.md/ADR updates. Use when decisions should persist in the codebase.
---

Run a `$grilling` session, using the `$domain-modeling` skill.

Use this for repo-backed ideas where the output should leave durable context. Read `CONTEXT.md`, relevant `spec-prd/` material, `docs/adr/`, and `docs/agents/matt-skill-workflow.md` before the interview if they are relevant to the idea.

During grilling:

- Drive toward a shared design concept, not a static plan.
- If a question can be answered by repo exploration, explore instead of asking.
- If a question needs primary-source facts, pause and route to `$research`.
- If a question needs a runnable answer or visual/state-model feel, route to `$prototype` and bring the verdict back.
- Update `CONTEXT.md` for clarified domain language and create ADRs only for hard-to-reverse decisions or unusual tradeoffs.
- Create glossary/ADR updates before `$to-prd` or `$to-issues` so downstream documents use the accepted language and decision record.
- For greenfield or setup-heavy work, grill the Agent Experience (AX): feedback loops, technology choices, module shape, and testing strategy.

Do not enact the plan. End with the resolved claim, remaining unknowns, and the next skill to use (`$research`, `$prototype`, `$to-prd`, `$to-issues`, or `$implement`).
