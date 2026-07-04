---
name: domain-modeling
description: Sharpen domain language and ADRs. Use for glossary terms, ubiquitous language, architectural decisions, or skill-driven domain updates.
---

# Domain Modeling

Actively sharpen the domain model: challenge terms, test scenarios, and write glossary/decision updates as they crystallize. Merely reading `CONTEXT.md` for vocabulary is not this skill.

## File structure

Most repos have one root `CONTEXT.md` and `docs/adr/`. If `CONTEXT-MAP.md` exists, follow it to the relevant per-context `CONTEXT.md` and ADR directory.

Create files lazily — only when you have something to write. If no `CONTEXT.md` exists, create one when the first term is resolved. If no `docs/adr/` exists, create it when the first ADR is needed.

## During the session

- **Challenge conflicts**: if user language contradicts `CONTEXT.md`, surface the conflict immediately and ask which meaning wins.
- **Sharpen vague terms**: propose canonical terms for overloaded words.
- **Stress-test relationships**: invent concrete edge-case scenarios that force precise boundaries.
- **Check code claims**: when the user states how something works, verify against code and surface contradictions.
- **Update inline**: when a term is resolved, update `CONTEXT.md` immediately using [CONTEXT-FORMAT.md](CONTEXT-FORMAT.md).

`CONTEXT.md` should be totally devoid of implementation details. Do not treat `CONTEXT.md` as a spec, a scratch pad, or a repository for implementation decisions. It is a glossary and nothing else.

## ADRs

Only offer to create an ADR when all three are true:

1. **Hard to reverse** — the cost of changing your mind later is meaningful
2. **Surprising without context** — a future reader will wonder "why did they do it this way?"
3. **The result of a real trade-off** — there were genuine alternatives and you picked one for specific reasons

If any condition is missing, skip the ADR. Use [ADR-FORMAT.md](ADR-FORMAT.md).
