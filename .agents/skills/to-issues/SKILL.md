---
name: to-issues
description: Split a plan, spec, or PRD into tracer-bullet issues on the configured issue tracker.
---

# To Issues

Turn approved source material into independently grabbable tracer-bullet issues.

The issue tracker and triage label vocabulary should have been provided to you — run `$setup-matt-pocock-skills` if not.

Use `docs/agents/matt-skill-workflow.md` and `docs/agents/issue-tracker.md` as the repo-specific references for tracer-bullet issue shape and publishing location.

## Process

### 1. Gather context

Use the current conversation, source PRD/spec/plan, linked research/prototype verdicts, and issue tracker config. If the user passes an issue reference, fetch its full body and comments.

### 2. Explore the codebase (optional)

If codebase shape is not already known, explore enough to avoid stale or impossible slices. Use the project glossary and respect ADRs.

If a small prefactor is needed to make a slice viable, make it an explicit issue. Link every relevant research artifact or prototype verdict from the issue that consumes it.

### 3. Draft vertical slices

Break the source into thin end-to-end slices, not horizontal layer work.

- Each slice delivers a narrow but COMPLETE path through every layer (schema, API, UI, tests)
- A completed slice is demoable or verifiable on its own
- Any prefactoring should be done first
- Each slice preserves one explicit claim and references the parent PRD/spec and user stories it covers
- Avoid speculative file paths, function names, or class names that may go stale before implementation

If a slice still needs product, compliance, design, architecture judgement, or manual acceptance, mark it HITL instead of ready for AFK implementation. Add a final HITL QA issue when manual verification is required across multiple slices; if all verification is automated, state that no separate QA issue is needed.

### 4. Quiz the user

Present the proposed breakdown as a numbered list. For each slice, show:

- **Title**: short descriptive name
- **Mode**: `AFK` or `HITL`
- **Blocked by**: which other slices (if any) must complete first
- **User stories covered**: which user stories this addresses (if the source material has them)

Ask the user:

- Does the granularity feel right? (too coarse / too fine)
- Are the dependency relationships correct?
- Are the correct slices marked AFK versus HITL?
- Should any slices be merged or split further?

Iterate until the user approves the breakdown.

### 5. Publish the issues to the issue tracker

For each approved slice, publish one issue. AFK slices get `ready-for-agent`; HITL or manual-QA slices get `ready-for-human` unless the user explicitly instructs otherwise.

Publish issues in dependency order (blockers first) so you can reference real issue identifiers in the "Blocked by" field.

Use [ISSUE-TEMPLATE.md](ISSUE-TEMPLATE.md) for each issue body.

Do NOT close or modify any parent issue.
