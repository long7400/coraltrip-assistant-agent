# Issue Template

Use this body for every issue published by `$to-issues`.

```markdown
# <short issue title>

Status: <ready-for-agent | ready-for-human>
Type: <feature | bug | research | prototype | task | decision>
Source: <parent PRD/spec/path>

## Parent

A reference to the parent issue on the issue tracker, if the source was an existing issue. Omit if not applicable.

## Claim

One precise outcome this issue must deliver. Preserve the claim; if the outcome requires a specific mechanism, do not substitute a different mechanism without user acceptance.

## Mode

AFK if an agent can implement it from the issue without unresolved human judgement, or HITL if it requires product, compliance, design, architecture, or manual QA judgement.

## What to build

A concise description of the end-to-end behavior. Avoid layer-by-layer implementation detail, speculative paths, and stale code names.

Exception: inline the decision-rich part of a prototype snippet when it encodes an accepted decision more precisely than prose.

## User stories covered

- Numbered references from the parent PRD, or "None / not applicable".

## Acceptance criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Blocked by

- Blocking ticket reference, or "None - can start immediately".

## Verification

- Command, test, artifact, screenshot, or review proof required to close this issue.
```
