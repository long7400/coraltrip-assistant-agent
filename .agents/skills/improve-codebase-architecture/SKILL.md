---
name: improve-codebase-architecture
description: Scan for architecture deepening opportunities, write an HTML report, then grill the chosen refactor into an issue.
---

# Improve Codebase Architecture

Surface architectural friction and propose **deepening opportunities** that improve testability and AI navigation.

Use `$codebase-design` vocabulary exactly: module, interface, depth, seam, adapter, leverage, locality. Use `CONTEXT.md` for domain names and ADRs for decisions not to re-litigate.

## Process

### 1. Explore

Read the domain glossary and relevant ADRs first. Use an exploration sub-agent when available; set `fork_context=false`, wait for completion, use a maximum timeout of one hour, and request progress after 30 minutes. If unavailable, explore directly.

Look for:

- Where does understanding one concept require bouncing between many small modules?
- Where are modules **shallow** — interface nearly as complex as the implementation?
- Where have pure functions been extracted just for testability, but the real bugs hide in how they're called (no **locality**)?
- Where do tightly-coupled modules leak across their seams?
- Which parts of the codebase are untested, or hard to test through their current interface?

Apply the **deletion test** to anything you suspect is shallow: would deleting it concentrate complexity, or just move it? A "yes, concentrates" is the signal you want.

### 2. Present candidates as an HTML report

Write a self-contained HTML file outside the repo: `<tmpdir>/architecture-review-<timestamp>.html` (`$TMPDIR`, `/tmp`, or `%TEMP%`). Open it for the user and report the absolute path.

Use [HTML-REPORT.md](HTML-REPORT.md) for the scaffold and visual patterns. Each candidate must include before/after visualization. Use Mermaid for graph-shaped relationships and hand-built CSS/SVG for editorial visuals.

For each candidate, render a card with:

- **Files** — which files/modules are involved
- **Problem** — why the current architecture is causing friction
- **Solution** — plain English description of what would change
- **Benefits** — explained in terms of locality and leverage, and how tests would improve
- **Before / After diagram** — side-by-side, custom-drawn, illustrating the shallowness and the deepening
- **Recommendation strength** — one of `Strong`, `Worth exploring`, `Speculative`, rendered as a badge

End the report with a **Top recommendation** section: which candidate you'd tackle first and why.

Use `CONTEXT.md` vocabulary for the domain and `$codebase-design` vocabulary for architecture.

If a candidate contradicts an ADR, surface it only when the friction is real enough to revisit the decision; mark the conflict in the card.

Do NOT propose interfaces yet. After the file is written, ask the user: "Which of these would you like to explore?"

### 3. Grilling loop

Once the user picks a candidate, run `$grilling` to settle constraints, dependencies, module shape, seam contents, adapters, and tests.

Run `$domain-modeling` inline as decisions crystallize:

- **Naming a deepened module after a concept not in `CONTEXT.md`?** Add the term to `CONTEXT.md`. Create the file lazily if it doesn't exist.
- **Sharpening a fuzzy term during the conversation?** Update `CONTEXT.md` right there.
- **User rejects the candidate with a load-bearing reason?** Offer an ADR only when future reviews need that reason to avoid re-suggesting it.
- **Want to explore alternative interfaces for the deepened module?** Run the `$codebase-design` skill and use its design-it-twice parallel sub-agent pattern.

When the user approves a design, publish a refactor issue through the configured issue tracker (`docs/agents/issue-tracker.md`). The issue should preserve the chosen module/interface/seam, the hidden implementation, dependency/adapters strategy, acceptance criteria, and verification. Mark it `ready-for-human` while architecture judgement is still unresolved; mark it `ready-for-agent` only when the implementation claim is bounded enough for AFK work.
