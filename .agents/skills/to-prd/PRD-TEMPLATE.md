# PRD Template

Use this body for every PRD produced by `$to-prd`.

```markdown
## Problem Statement

The problem from the user's perspective.

## Solution

The solution from the user's perspective.

## User Stories

A numbered list covering the feature:

1. As an <actor>, I want a <feature>, so that <benefit>

## Source Material

Conversation decisions, specs, research artifacts, prototype verdicts, ADRs, and glossary terms this PRD depends on.

## Module And Seam Decisions

Chosen module boundaries and testing seams. Include public interface, hidden implementation detail, highest useful test seam, and any CoralTrip adapter boundary involved.

## Agent Experience Decisions

Feedback loops and repo ergonomics the PRD depends on: typechecks, tests, format/lint/pre-commit, smoke checks, hard-to-reverse technology choices, and AX setup required before AFK implementation. Use `Existing baseline is sufficient` if no new AX work is needed.

## Implementation Decisions

Implementation decisions that were accepted: modules, interfaces, architectural decisions, schema changes, API contracts, and specific interactions.

Do not include speculative file paths or code snippets. Exception: inline the decision-rich part of a prototype snippet when it encodes an accepted decision more precisely than prose.

## Testing Decisions

Behavioral testing decisions: which modules/seams to test, prior art in the repo, and what makes those tests valuable.

## Out of Scope

Things this PRD explicitly excludes.

## Human Decisions Still Required

Unresolved product, design, compliance, or architecture decisions that remain HITL. Use `None` if empty.

## Further Notes

Any remaining useful notes.
```
