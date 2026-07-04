---
name: to-prd
description: Synthesize current conversation into a PRD and publish it as source material for issues. No interview.
---

Produce a PRD from current conversation context and codebase understanding. Do not interview the user; synthesize what is already known.

The issue tracker and triage label vocabulary should have been provided to you — run `$setup-matt-pocock-skills` if not.

Use `docs/agents/matt-skill-workflow.md` as the workflow reference when deciding what belongs in the PRD versus later issues.

## Process

1. **Gather source material.** Explore the repo if needed. Use the project glossary and respect ADRs. Pull in research artifacts, prototype verdicts, handoff notes, source PRDs/specs, and user decisions the PRD depends on.

2. **Choose module and seam shape.** Prefer existing seams. Use the highest useful seam and the fewest new seams possible. Identify the public interface, hidden implementation details, highest test seam, and any CoralTrip adapter boundary.

   If the repo is greenfield or lacks reliable feedback loops, include Agent Experience (AX) decisions before product work: typecheck, tests, formatter/linter, smoke checks, technology choices, module shape, and testing strategy.

   Check with the user that the seams match their expectations.

3. **Publish the PRD.** Use [PRD-TEMPLATE.md](PRD-TEMPLATE.md), then publish it to the issue tracker as source material for `$to-issues`. The PRD itself is not `ready-for-agent`; child issues carry `ready-for-agent` or `ready-for-human`.

The PRD is a destination document, not an implementation script. Avoid speculative file paths, function names, or class names unless they already exist or were accepted as a decision.
