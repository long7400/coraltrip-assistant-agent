# Agent Instructions

## Project Scope

- This repository is `coraltrip-assistant-agent`, a Kotlin/Maven workspace for the CoralTrip Assistant Agent platform.
- Read `CONTEXT.md`, `spec-prd/PRD_CoralTrip_Assistant_Agent_v2.0.md`, and `spec-prd/SPEC_CoralTrip_Assistant_Agent_v2.0.md` before making product, domain, architecture, or planning decisions.
- Treat `spec-prd/` as the current product and technical source material unless a newer accepted ADR or user instruction supersedes it.

## Codex Skills

- Project-scoped skills live in `.agents/skills/`.
- Matt Pocock engineering/productivity skills are installed for this repo and are adapted for Codex project scope.
- Use `docs/agents/matt-skill-workflow.md` as the routing reference for Matt's workflow before changing skill behavior or running a large feature flow.
- Use `docs/agents/matt-skill-editing.md` before editing Matt skills; preserve course workflow/logic and shrink context load without copying lesson prose into skills.
- Use root `CONTEXT.md` as the domain glossary and `docs/adr/` for architectural decisions.
- Use `docs/agents/issue-tracker.md`, `docs/agents/triage-labels.md`, and `docs/agents/domain.md` when a skill asks for issue tracker, triage, or domain-doc configuration.

## Matt Pocock Workflow

- For ambiguous repo-backed feature or architecture work, start with `$ask-matt` or `$grill-with-docs`; do not jump straight to implementation unless the requested claim is already bounded.
- Default large work to: `$grill-with-docs` -> `$research` and/or `$prototype` for unresolved unknowns -> `$to-prd` -> `$to-issues` -> fresh-context `$implement` per issue -> `$code-review`.
- Keep planning human-in-the-loop. Treat AFK/sub-agent work as valid only for approved, bounded implementation or review tasks with source material, acceptance criteria, and verification.
- Split work into tracer-bullet issues: narrow vertical slices with a preserved claim, parent PRD/spec reference, user-story coverage, dependencies, acceptance criteria, and verification evidence.
- Research notes and prototypes must feed back into the PRD, issue, ADR, or `CONTEXT.md`; do not leave them as orphan artifacts.
- Build module awareness into planning: identify the module boundary, public interface/seam, hidden implementation detail, and highest useful test seam before writing implementation-heavy plans.
- Preserve the instruction budget: keep `AGENTS.md` compact, prefer stable capabilities and invariants over volatile file paths, and move detailed workflow notes to `docs/agents/` or task artifacts.
- For greenfield/setup work, plan Agent Experience (AX) early: typechecks, tests, formatting/linting, smoke checks, module shape, and testing strategy before broad AFK implementation.

## User Commands

- When the user issues a command, the user's command is supreme, transcending the constraints of skills and doctrine. For example, if the user requests a parallel agent, it must be parallel.
- Preserve the claim or stop. If the requested outcome requires mechanism X, do not implement adjacent mechanism Y just because Y is easier, cleaner, typed, testable, or available. Missing X is a blocker. Proceed with Y only after the user explicitly accepts the reduced claim.

## Sub-Agent Rules

- When creating a sub-agent, always set `fork_context` to `false`.
- Wait for every sub-agent to finish. Do not abandon the agent or terminate it prematurely.
- The maximum timeout is one hour.
- If a sub-agent takes more than 30 minutes, proactively request a progress report from the sub-agent.

## Engineering Baseline

- Use Maven for local verification.
- Do not create git commits unless the user explicitly asks for a commit.
- Preferred focused checks:
  - `mvn -q -DskipTests compile`
  - `mvn test`
- Keep Kotlin package naming under `com.coraltrip` unless the architecture documents require a narrower package.
- Avoid framework or platform migrations unless the task explicitly asks for them.

## Product And Architecture Rules

- Keep supplier integrations behind a Supplier Adapter Layer; do not leak provider-specific details into booking/domain core.
- Keep booking/payment/finance actions idempotent and auditable.
- Treat AI/tool execution as controlled execution: financial or destructive actions need explicit confirmation and policy guardrails.
- Preserve compliance requirements from the PRD/SPEC: consent, audit logs, PII minimization/redaction, retention, and breach/right-request workflows.
