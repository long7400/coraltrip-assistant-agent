# Matt Skill Workflow

This repo uses the Matt Pocock skills as a project workflow, not as isolated commands. Keep this file as the compact routing reference for agents; keep detailed product truth in `spec-prd/`, `CONTEXT.md`, and `docs/adr/`.

## Core Route

1. **Grill**: use `$grill-with-docs` for repo-backed ideas. The goal is a shared design concept, not a static plan. Resolve business, UX, architecture, and testing uncertainty before implementation starts.
2. **Research when facts are missing**: use `$research` for primary-source reading. Research must return to the main thread and feed a PRD, issue, ADR, or `CONTEXT.md`; stale standalone research is debt.
3. **Prototype when the answer must be felt or run**: use `$prototype` for uncertain state models, business logic, or UI choices. Keep the question, verdict, and decision; delete or isolate the throwaway code.
4. **PRD**: use `$to-prd` once the destination is clear enough. The PRD should explain user value, user stories, module boundaries, testing seams, accepted tradeoffs, and unresolved human decisions.
5. **Issues**: use `$to-issues` to create tracer-bullet issues. Prefer dependency graphs over rigid multi-phase plans. Each issue should be independently grabbable, narrow, vertical, and tied back to parent PRD/user stories.
6. **Implementation**: use `$implement` on one approved issue or small PRD at a time, usually in fresh context. Drive with `$tdd` at agreed seams, run focused checks often, and run the broad check at closeout.
7. **Review**: use `$code-review` before handoff or merge. Review both spec fit and standards. Capture process improvements as suggestions unless the user explicitly asks to update skills or instructions.

## Steering Rules

- **Own the process**: these skills are a workflow to adapt, not a framework to obey blindly. User commands and repo constraints still win.
- **Respect the instruction budget**: keep `AGENTS.md` short. Put stable, always-needed rules there; put detailed workflow guidance in `docs/agents/`; put task-specific detail in PRDs/issues/ADRs.
- **Avoid stale structure docs**: document capabilities, vocabulary, invariants, and accepted decisions. Avoid volatile file paths, class names, or generated repo maps unless they are current source material for a specific task.
- **Use progressive disclosure**: skills should route to references and artifacts instead of carrying every detail in one global prompt.
- **Edit skills through the contract**: before changing Matt skills, use `docs/agents/matt-skill-editing.md`; preserve workflow logic and prune context load, starting with descriptions.

## HITL And AFK

- **HITL by default**: grilling, PRD shaping, issue breakdown, architecture decisions, user-facing design judgement, compliance/policy decisions, and final acceptance.
- **AFK only when bounded**: implementation or review of an approved issue with clear claim, source material, acceptance criteria, verification command/artifact, and no unresolved business judgement.
- **Manual QA is HITL**: when acceptance requires human feel, design judgement, compliance judgement, or clicking through a product flow, create or preserve a `ready-for-human` QA issue instead of smuggling it into AFK implementation.
- **Repo override**: any sub-agent must use `fork_context=false`, must be awaited, may run for at most one hour, and needs a progress request after 30 minutes.

## Feedback Loops And AX

Agents need concrete feedback from the repo. Prefer existing typechecks, tests, formatters, linters, runtime smoke checks, and pre-commit style checks over invented verification.

For greenfield work or a thin skeleton, design **Agent Experience (AX)** before or alongside UX:

- feedback loops: typecheck, tests, formatter, lint/pre-commit, runnable smoke checks,
- technology choices that are hard to reverse,
- module shape and deep-module candidates,
- testing strategy: highest seams, test database/mocks, and integration boundaries.

If AX is not in place, the first PRD/issues may need to establish it before product slices can safely run AFK.

## Tracer-Bullet Issues

A tracer bullet is a thin end-to-end path through the product. Avoid horizontal slices such as "build all schemas", "build all services", or "build all UI" unless the issue is explicit prefactoring.

Each issue should include:

- **Claim**: one precise outcome that must be preserved.
- **Parent**: PRD/spec/source reference.
- **Mode**: `AFK` only when no unresolved human judgement remains; otherwise `HITL`.
- **User stories covered**: numbered references from the PRD when available.
- **Blocked by**: real dependency references or `None`.
- **Acceptance criteria**: observable behavior, not internal steps.
- **Verification**: command, test, artifact, screenshot, or review proof.

## Module Awareness

Plan module shape before code shape. A good module hides meaningful behavior behind a small interface at a stable seam. When planning PRDs or issues, record:

- the existing or proposed module boundary,
- the public interface or seam callers should depend on,
- the implementation detail that should stay hidden,
- the highest useful test seam,
- any adapter boundary required by CoralTrip architecture.

Avoid plans that name speculative functions, files, or classes unless the name is already accepted source truth. Those details go stale quickly.

## ADRs And Glossary

`$grill-with-docs` should create the language foundation before downstream documents are written:

- update `CONTEXT.md` when a domain term is introduced, clarified, rejected, or overloaded,
- create an ADR for a hard-to-reverse design choice or an unusual tradeoff,
- record why the decision was made, what alternatives were considered, and what constraints mattered,
- do this before `$to-prd` and `$to-issues` so PRDs, issue titles, tests, and module names use the right language.

## Context Hygiene

- Keep grill -> research/prototype decisions -> PRD -> issue split in one coherent context while it remains sharp.
- Use `$handoff` when the thread must branch, when a prototype/research detour needs a fresh session, or before context becomes degraded.
- Clear or compact only at phase boundaries, never in the middle of a design or implementation loop.
