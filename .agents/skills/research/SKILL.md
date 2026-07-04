---
name: research
description: Primary-source research by sub-agent, saved as cited Markdown. Use for docs/API facts or reading legwork.
---

Spin up a research sub-agent to do the reading legwork. In this repo, every sub-agent must be created with `fork_context=false`; wait for it to finish before continuing. Do not abandon it or continue past the research result. Use a maximum timeout of one hour, and if it takes more than 30 minutes, request a progress report.

If the current Codex surface cannot create sub-agents, stop and ask whether the user wants you to perform the research locally in the main context instead.

Its job:

1. Investigate the question against **primary sources** — official docs, source code, specs, first-party APIs — not a secondary write-up of them. Follow every claim back to the source that owns it.
2. Write the findings to a single Markdown file, citing each claim's source.
3. Save it where the repo already keeps such notes; match the existing convention, and if there is none, use `.scratch/<effort>/research/` and say where.
4. Include a **Use this result in** section naming the PRD, issue, ADR, `CONTEXT.md` update, or follow-up decision that should consume the research.

Research has a lifecycle. Do not leave a note as free-floating context: after reading it, either fold the finding into the PRD/issues/ADR/`CONTEXT.md`, mark the note superseded, or delete it if it was purely temporary.
