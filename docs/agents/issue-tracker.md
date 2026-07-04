# Issue Tracker

Issues and planning work for this repo currently live as local markdown files under `.scratch/`.

This repo has no remote issue tracker configured yet. Do not use `gh`, `glab`, Linear, Jira, or another external tracker unless the user explicitly switches this configuration.

## Local Markdown Layout

- PRDs and durable product/technical source material live in `spec-prd/` unless superseded by a user-approved destination.
- Agent-created work packets live under `.scratch/<effort>/`.
- Issues live under `.scratch/<effort>/issues/NN-<slug>.md`, numbered from `01`.
- Use `Status:` to record triage state.
- Use `Type:` to record the work type, such as `feature`, `bug`, `research`, `prototype`, `task`, or `decision`.

## Issue Template

```markdown
# <short issue title>

Status: needs-triage
Type: task
Source: <PRD/spec/path or conversation reference>

Mode: <AFK | HITL | not applicable>

## Parent

<parent PRD/spec/issue path or "None">

## Claim

<one precise outcome this issue must deliver>

## Context

<source facts, constraints, and links>

## User Stories Covered

- <numbered PRD user story reference, or "None / not applicable">

## Blocked By

- <blocking issue reference, or "None">

## Acceptance Criteria

- <observable requirement>

## Verification

- <command, test, artifact, screenshot, or review proof>
```

## Operations

- Create issues by writing a new markdown file in the relevant `.scratch/<effort>/issues/` directory.
- Split large plans into tracer-bullet issues: each issue should be a narrow vertical slice with its own claim, dependency relationship, acceptance criteria, and verification.
- Keep implementation details stable enough for an agent to act, but avoid speculative file/function names that may go stale before the issue is picked up.
- Read all linked source documents before changing issue status.
- Keep `.scratch/` aligned with durable truth in `spec-prd/`, `CONTEXT.md`, and `docs/adr/`; do not let scratch files become the only source of product truth.
