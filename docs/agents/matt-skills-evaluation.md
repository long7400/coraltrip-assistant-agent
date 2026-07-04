# Matt Skills Evaluation

Date: 2026-07-04

Scope: every project skill under `.agents/skills/*/SKILL.md`, plus companion reference files directly linked by each skill when relevant.

Validation command used per skill:

```bash
python3 /Users/long7400/.codex/skills/.system/skill-creator/scripts/quick_validate.py .agents/skills/<skill-name>
```

Full sweep result on 2026-07-04: 21/21 skills valid.

## Method

- Read `skill-creator` before editing skills.
- Treat HTML lessons `001-085` as primary where available; read SRT/VTT for video-only lessons and office-hours material (`086-092`) where relevant.
- Compare each skill against the lesson intent, progressive disclosure, instruction budget, repo/user constraints, and hallucination risk.
- Patch only when a concrete gap was found. Avoid copying course notes into every skill.

## Context-Reduction Pass

Date: 2026-07-04

Reason: user asked for an additional prompt/skill-engineering pass that preserves the course content, workflow, and logic while reducing context bloat and hallucination risk.

Evidence used:

- Current skill state and this audit file.
- Course evidence already mapped below, plus targeted rereads of lessons `030`, `031`, `032`, and SRT/VTT material from `091` and `092` on progressive disclosure, procedure/ability skills, compact skills, and pruning.
- `$skill-creator` guidance: concise skills, progressive disclosure, frontmatter description as trigger surface, and validation.
- Official Codex guidance: skills use progressive disclosure; descriptions should be concise, scoped, and front-loaded because they drive implicit matching; AGENTS.md should stay compact.
- Official OpenAI prompting guidance: keep instructions concrete, put constraints/verification in the prompt, and remove outdated or conflicting prompt text instead of accumulating it.

Updates made:

- Shortened frontmatter descriptions for 13 skills to reduce always-loaded routing context while preserving trigger words and branches.
- Rewrote `$writing-great-skills` from a repeated glossary-style essay into a compact rewrite loop; full definitions remain in `GLOSSARY.md` via progressive disclosure.
- Aligned `$writing-great-skills` glossary with Codex: `description` remains required; explicit-only behavior belongs in `agents/openai.yaml` policy rather than deleting frontmatter.
- Added `docs/agents/matt-skill-editing.md` as the project-level editing contract for future Matt skill changes.
- Added a compact `AGENTS.md` pointer to that contract instead of expanding always-loaded instructions.
- Added stable context vocabulary: `Context pointer`, `Procedure skill`, `Ability skill`, and `Leading word`.
- Updated `docs/agents/matt-skill-workflow.md` to route skill edits through the new editing contract.

Validation after pass:

- `SKILL.md` line count changed from 1408 observed before the pass to 1357 after the pass.
- Description total after the pass: 2207 characters across 21 skills.
- Full validation sweep: `ALL_SKILLS_VALID 21`.

Preservation check:

- No procedure route was changed: grill -> research/prototype -> PRD -> issues -> implementation/TDD -> review remains intact.
- No HITL/AFK classification was weakened.
- No sub-agent-dependent workflow was replaced with a local approximation.
- No lesson transcript prose was copied into skills.

## Body-Command Rewrite Pass

Date: 2026-07-04

Reason: user clarified that shortening descriptions was not enough; the command/body text inside skills also needed audit and rewrite against the HTML course material.

Evidence used:

- Parsed the offline course HTML index and all 85 lesson HTML files under `/Users/long7400/Learn/AI/All Lessons/html/`.
- Used HTML lessons `001-085` as the primary course source for workflow principles: context limits, progressive disclosure, skills as steering, feedback loops, red-green, tracer bullets, AFK/HITL, research, prototypes, codebase design, and final workflow.
- Re-read `$skill-creator`, `$writing-great-skills`, and this editing contract before patching.

Updates made:

- Rewrote long bodies into operational checklists and completion gates for `teach`, `diagnosing-bugs`, `setup-matt-pocock-skills`, `to-issues`, `codebase-design`, `triage`, `to-prd`, `code-review`, `domain-modeling`, `tdd`, `improve-codebase-architecture`, and `ask-matt`.
- Moved long output contracts and review baselines behind explicit pointers:
  - `.agents/skills/to-issues/ISSUE-TEMPLATE.md`
  - `.agents/skills/to-prd/PRD-TEMPLATE.md`
  - `.agents/skills/code-review/SMELL-BASELINE.md`
  - `.agents/skills/setup-matt-pocock-skills/agent-skills-block.md`
  - `.agents/skills/triage/NEEDS-INFO-TEMPLATE.md`
- Preserved stop/ask gates, HITL/AFK classification, required sub-agent mechanics, issue/PRD output fields, and verification requirements.
- Removed explanatory prose, motivational language, ASCII diagrams, repeated definitions, and inline templates that were better expressed as references.

Validation after pass:

- `SKILL.md` line count changed from 1357 after the description pass to 931 after the body-command pass.
- Full validation sweep: `ALL_SKILLS_VALID 21`.
- Markdown reference check: `ALL_MARKDOWN_LINKS_EXIST`.

Preservation check:

- The main flow still routes grill -> research/prototype -> PRD -> issues -> implementation/TDD -> review.
- `$code-review`, `$research`, and design-it-twice still require real sub-agent mechanics rather than local approximation.
- `$to-prd` remains source material for `$to-issues`; whole PRDs are not labelled agent-ready implementation work.
- `$to-issues` still publishes tracer-bullet issues with Mode, Claim, acceptance criteria, dependencies, and verification.
- `$diagnosing-bugs` still blocks hypothesis work until a red-capable loop exists.

## Skill Audit Matrix

### `ask-matt`

- Skill path: `.agents/skills/ask-matt/SKILL.md`
- Sources read: HTML `001`, `022`, `025`, `026`, `083`, `084`, `085`; SRT `091`, `092`.
- Lesson principle: own the process; route through grill -> research/prototype -> PRD -> issues -> implementation -> review; keep procedure skills separate; stop before substituting a local pass for required sub-agents.
- Current behavior: router already captured the main flow, context hygiene, greenfield AX, and vocabulary skills.
- Decision/update: updated routing language so repo-backed decisions prefer `$grill-with-docs`; added a sub-agent-dependent-step guard for research/review/design-it-twice; later compacted body routing prose while preserving the same flow.
- Validation: pass in 2026-07-04 full sweep.

### `code-review`

- Skill path: `.agents/skills/code-review/SKILL.md`
- Sources read: HTML `047`, `083`; SRT `089`, `090`, `092` review sections.
- Lesson principle: automated review is valuable after implementation because it can carry standards/review load that would overload the implementation context; review should compare the diff to spec and standards.
- Current behavior: two-axis Standards + Spec review, with smell baseline and fixed-point diff.
- Decision/update: added explicit stop/ask behavior if sub-agent tooling is unavailable, preserving the parallel-review claim; later moved the smell baseline to `SMELL-BASELINE.md` and kept a required pointer in the Standards axis.
- Validation: pass in 2026-07-04 full sweep.

### `codebase-design`

- Skill path: `.agents/skills/codebase-design/SKILL.md`
- Companion files read: `DEEPENING.md`, `DESIGN-IT-TWICE.md`.
- Sources read: HTML `079`, `080`, `081`, `082`; SRT `091` procedure-vs-ability discussion.
- Lesson principle: deep modules give AI better navigation and test seams; design vocabulary can be an ability skill used by other procedures; design-it-twice needs independent alternative designs.
- Current behavior: strong shared vocabulary and progressive disclosure into deepening/design-it-twice references.
- Decision/update: added a guard in `DESIGN-IT-TWICE.md`; later compacted the ability-skill body by removing diagrams/examples and preserving terms, checks, relationships, and reference pointers.
- Validation: pass in 2026-07-04 full sweep.

### `diagnosing-bugs`

- Skill path: `.agents/skills/diagnosing-bugs/SKILL.md`
- Companion file read: `scripts/hitl-loop.template.sh` was identified as the human-loop fallback referenced by the skill.
- Sources read: HTML `014`, `016`, `047`, `053`, `054`; SRT `089` feedback/review comments.
- Lesson principle: agents need concrete feedback loops; no hallucinated theory before a real signal; bugs should be locked down with a regression test at the right seam.
- Current behavior: already forces a tight red-capable loop before hypothesis, requires minimization, ranked falsifiable hypotheses, cleanup, and architecture follow-up when no seam exists.
- Decision/update: preserved the red-capable loop gate and phase order, but rewrote the body from explanatory prose into a stricter command ladder.
- Validation: pass in 2026-07-04 full sweep.

### `domain-modeling`

- Skill path: `.agents/skills/domain-modeling/SKILL.md`
- Companion files read: `CONTEXT-FORMAT.md`, `ADR-FORMAT.md`.
- Sources read: HTML `085`; SRT `088`, `091` domain-modeling/ability-skill discussion.
- Lesson principle: glossary and ADRs should be created during grilling before PRDs/issues so downstream artifacts use accepted language and decision records.
- Current behavior: actively challenges terms, updates `CONTEXT.md` inline, and offers ADRs only for hard-to-reverse surprising tradeoffs.
- Decision/update: compacted file-layout explanation and session rules while preserving inline glossary updates and ADR criteria.
- Validation: pass in 2026-07-04 full sweep.

### `grill-me`

- Skill path: `.agents/skills/grill-me/SKILL.md`
- Sources read: HTML `022`, `023`, `085`; SRT `089`, `091`, `092`.
- Lesson principle: grill-me is the stateless interview; grill-with-docs is the codebase/doc-preserving variant. Procedure invocation avoids nondeterministic skill pickup.
- Current behavior before update: delegated to `$grilling`, but description overlapped too much with `$grill-with-docs`.
- Decision/update: narrowed description/body to stateless, non-repo-backed use and updated `agents/openai.yaml` text.
- Validation: pass in 2026-07-04 full sweep.

### `grill-with-docs`

- Skill path: `.agents/skills/grill-with-docs/SKILL.md`
- Sources read: HTML `022`, `023`, `084`, `085`; SRT `088`, `091`.
- Lesson principle: repo-backed grilling should capture shared language and ADRs before PRD/issues; greenfield requires AX questions early.
- Current behavior before update: body captured the durable-doc workflow, but description did not strongly distinguish repo-backed use.
- Decision/update: strengthened description and OpenAI metadata to emphasize repo-backed plans and persistent docs.
- Validation: pass in 2026-07-04 full sweep.

### `grilling`

- Skill path: `.agents/skills/grilling/SKILL.md`
- Sources read: HTML `022`, `023`; SRT `092` grilling/fidelity notes.
- Lesson principle: establish shared design concept one question at a time; explore the repo instead of asking answerable questions; route unknown facts/prototypes rather than faking certainty.
- Current behavior: already one-question-at-a-time, explores when possible, and pauses for `$research`/`$prototype` when conversation cannot settle the question.
- Decision/update: no change.
- Validation: pass in 2026-07-04 full sweep.

### `handoff`

- Skill path: `.agents/skills/handoff/SKILL.md`
- Sources read: HTML `025`, `026`.
- Lesson principle: prefer fresh context and handoff files over repeated compaction sediment; save temp handoff, suggest next skills, reference existing artifacts instead of duplicating.
- Current behavior before update: matched handoff shape but did not explicitly require reporting the temp file path.
- Decision/update: added instruction to tell the user the absolute path after writing the handoff.
- Validation: pass in 2026-07-04 full sweep.

### `implement`

- Skill path: `.agents/skills/implement/SKILL.md`
- Sources read: HTML `043`, `047`, `053`, `054`, `056`, `061`, `083`; SRT `089`, `092` review/implementation split.
- Lesson principle: implementation should be one bounded issue/slice, driven by real feedback loops and red-green slices; review load should not overload implementation.
- Current behavior before update: preserved issue claim, required source material, feedback loops, TDD, and code review.
- Decision/update: changed sub-agent-unavailable review fallback from automatic local review to stop/ask, preserving the requested review mechanism.
- Validation: pass in 2026-07-04 full sweep.

### `improve-codebase-architecture`

- Skill path: `.agents/skills/improve-codebase-architecture/SKILL.md`
- Companion file read: `HTML-REPORT.md`.
- Sources read: HTML `079`, `080`, `081`, `082`; SRT `091` command/ability split.
- Lesson principle: surface deepening candidates, let the human pick, explore/design the chosen one, then turn the approved design into a backlog item.
- Current behavior before update: candidate report and grilling were present; issue creation after approved design was missing.
- Decision/update: added closeout to publish a refactor issue after user approval; later compacted exploration/report/grilling prose and kept `HTML-REPORT.md` as the detailed visual scaffold.
- Validation: pass in 2026-07-04 full sweep.

### `prototype`

- Skill path: `.agents/skills/prototype/SKILL.md`
- Companion files read: `LOGIC.md`, `UI.md`.
- Sources read: HTML `075`, `076`, `077`, `078`; SRT `090`, `092` prototype/fidelity sections.
- Lesson principle: prototype answers one question with throwaway code; branch into logic TUI or UI variants; capture a verdict and feed it back into PRD/issues/ADR/CONTEXT.
- Current behavior: already separates logic/UI branches, requires one command to run, no persistence by default, visible state, verdict capture, and delete/absorb cleanup.
- Decision/update: no change.
- Validation: pass in 2026-07-04 full sweep.

### `research`

- Skill path: `.agents/skills/research/SKILL.md`
- Sources read: HTML `072`, `073`, `074`; SRT `089` research/context-gathering notes.
- Lesson principle: research is HITL-ish reading against primary sources, produces a cited Markdown artifact, and must have a lifecycle so stale notes do not poison context.
- Current behavior before update: primary sources, cited file, destination section, and lifecycle were present.
- Decision/update: added stop/ask guard if sub-agent tooling is unavailable.
- Validation: pass in 2026-07-04 full sweep.

### `resolving-merge-conflicts`

- Skill path: `.agents/skills/resolving-merge-conflicts/SKILL.md`
- Sources read: HTML `005`, `011`, `047`; no dedicated merge-conflict Matt skill lesson was found in the lesson index.
- Lesson principle: merge/cherry-pick conflicts are real places where AI can help, but destructive reset/abort/commit actions must preserve work and follow user intent; run feedback loops after resolution.
- Current behavior before update: always resolve, never abort, and stage/commit automatically.
- Decision/update: changed abort/commit behavior to respect explicit user commands and repo rule against unsolicited commits; still resolves hunks and runs checks.
- Validation: pass in 2026-07-04 full sweep.

### `setup-matt-pocock-skills`

- Skill path: `.agents/skills/setup-matt-pocock-skills/SKILL.md`
- Companion files read: `issue-tracker-local.md`, `issue-tracker-github.md`, `issue-tracker-gitlab.md`, `triage-labels.md`, `domain.md`.
- Sources read: HTML `027`, `030`, `031`, `032`, `063`, `064`, `065`, `067`, `085`.
- Lesson principle: keep `AGENTS.md` compact; configure issue tracker, labels, and domain-doc layout once; use the actual repo workflow instead of assuming GitHub.
- Current behavior: explores repo state, asks one decision at a time, and writes setup docs from templates.
- Decision/update: added `Mode:` to local issue tracker seed; later removed repeated explainers and moved the reusable agent-instruction block to `agent-skills-block.md`.
- Validation: pass in 2026-07-04 full sweep.

### `tdd`

- Skill path: `.agents/skills/tdd/SKILL.md`
- Companion files read: `tests.md`, `mocking.md`.
- Sources read: HTML `047`, `053`, `054`; SRT `091`, `092` testing/review sections.
- Lesson principle: red-green-refactor is the feedback loop; one tracer-bullet test at a time; tests should hit agreed seams; broader standards cleanup can move to review to avoid implementation overload.
- Current behavior before update: strong test quality and seam guidance, but wording excluded refactor from the loop too strongly.
- Decision/update: changed loop rule to allow small same-slice refactor after green; later compressed anti-pattern explanations into pointers to `tests.md` and `mocking.md`.
- Validation: pass in 2026-07-04 full sweep.

### `teach`

- Skill path: `.agents/skills/teach/SKILL.md`
- Companion files read: `MISSION-FORMAT.md`, `RESOURCES-FORMAT.md`, `GLOSSARY-FORMAT.md`, `LEARNING-RECORD-FORMAT.md`.
- Sources read: SRT `089` teach-skill office-hours demo; HTML `031`, `032` skill/progressive-disclosure lessons.
- Lesson principle: teach is stateful, uses a workspace, builds high-trust resources, and records learning state rather than acting like a one-off explanation.
- Current behavior: mission, resources, reference docs, lessons, assets, notes, learning records, retrieval practice, and community/wisdom are already specified.
- Decision/update: rewrote the body into a state-loading, source-grounding, lesson-authoring, reference-update, and learning-record checklist.
- Validation: pass in 2026-07-04 full sweep.

### `to-issues`

- Skill path: `.agents/skills/to-issues/SKILL.md`
- Sources read: HTML `040`, `041`, `063`, `067`, `069`, `070`; SRT `090`, `092` issue/QA/review sections.
- Lesson principle: replace rigid multi-phase plans with dependency-graph issues; use tracer-bullet vertical slices; classify HITL vs AFK; create manual QA work when needed.
- Current behavior before update: tracer bullets, claim preservation, dependencies, and verification were present; HITL/AFK classification was not surfaced in the draft/published issue strongly enough.
- Decision/update: added `Mode`, AFK/HITL validation, HITL/manual-QA handling, and `ready-for-human`; later moved the full issue body to `ISSUE-TEMPLATE.md`.
- Validation: pass in 2026-07-04 full sweep.

### `to-prd`

- Skill path: `.agents/skills/to-prd/SKILL.md`
- Sources read: HTML `035`, `036`, `082`, `084`; SRT `090`, `092` PRD/checkpoint sections.
- Lesson principle: PRD is the destination document after grilling/research/prototype; module awareness should happen before implementation; greenfield PRDs need AX decisions.
- Current behavior before update: synthesized existing conversation without interviewing, pulled source material, sketched module/seam decisions, included AX and unresolved human decisions, and avoided stale file/function specificity. It still labelled the PRD itself `ready-for-agent`, which could let an AFK implementation agent pick up a whole destination document directly.
- Decision/update: changed PRD publishing so the PRD is source material for `$to-issues`; later moved the full PRD body to `PRD-TEMPLATE.md`.
- Validation: pass in 2026-07-04 full sweep.

### `triage`

- Skill path: `.agents/skills/triage/SKILL.md`
- Companion files read: `AGENT-BRIEF.md`, `OUT-OF-SCOPE.md`.
- Sources read: HTML `063`, `064`, `065`, `067`, `068`, `069`; SRT `090`, `092` issue/review sections.
- Lesson principle: incoming raw issues are not automatically agent-ready; verify the claim, collect missing info, preserve prior rejection knowledge, and classify ready-for-agent versus ready-for-human.
- Current behavior: state machine, verification step, grilling/domain-modeling when needed, agent brief format, out-of-scope KB, and AI disclaimer are already present.
- Decision/update: compacted triage steps and moved the needs-info notes template to `NEEDS-INFO-TEMPLATE.md`; state machine, verification, disclaimer, and brief/out-of-scope references remain.
- Validation: pass in 2026-07-04 full sweep.

### `writing-great-skills`

- Skill path: `.agents/skills/writing-great-skills/SKILL.md`
- Companion file read: `GLOSSARY.md`.
- Sources read: HTML `027`, `030`, `031`, `032`; SRT `091`, `092` skill-size/procedure-vs-ability/pruning sections.
- Lesson principle: skills should be predictable, compact, progressively disclosed, and split only when invocation/sequence earns the load. Keep meanings in one source of truth and prune no-ops/sediment.
- Current behavior: already encodes invocation, context load, cognitive load, router skill, information hierarchy, progressive disclosure, pruning, leading words, and failure modes.
- Decision/update: no change.
- Validation: pass in 2026-07-04 full sweep.

## Cross-Cutting Updates Outside Skill Folders

- `CONTEXT.md`: added `Manual QA Issue` to match HITL/AFK issue classification.
- `docs/agents/matt-skill-workflow.md`: added manual QA/HITL rule and `Mode` field for tracer-bullet issues.
- `docs/agents/issue-tracker.md`: added `Mode:` to the local issue template.

## Recheck Notes

- No skill was expanded with copied lesson prose.
- Sub-agent-dependent skills now stop/ask before substituting local main-context work.
- AFK issue publishing now distinguishes agent-ready implementation from human judgement and manual QA.
- Full validation sweep passed for all 21 skills on 2026-07-04.
