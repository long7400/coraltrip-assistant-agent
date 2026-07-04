# Domain Docs

This repo uses a single-context domain documentation layout.

## Sources

- Read root `CONTEXT.md` for the shared domain glossary.
- Read `docs/adr/` for accepted architectural decisions.
- Read `spec-prd/PRD_CoralTrip_Assistant_Agent_v2.0.md` for product requirements.
- Read `spec-prd/SPEC_CoralTrip_Assistant_Agent_v2.0.md` for architecture and technical requirements.
- Read backlog files in `spec-prd/` when splitting or implementing user stories.

## Writing Rules

- Update `CONTEXT.md` when a domain term is clarified, renamed, overloaded, or rejected.
- Create ADRs in `docs/adr/` only for decisions that are hard to reverse, affect module boundaries, or contradict prior assumptions.
- Use sequential ADR filenames: `0001-<slug>.md`, `0002-<slug>.md`, and so on.
- Do not create a separate `docs/domain/` tree unless this repo becomes multi-context.

## Consumer Rules

- Use terms exactly as defined in `CONTEXT.md` in issue titles, test names, module names, and architecture notes.
- If a proposed implementation contradicts an ADR, surface the contradiction explicitly before proceeding.
- If the PRD/SPEC and `CONTEXT.md` disagree, stop and ask whether to update the glossary, the source document, or the implementation target.
