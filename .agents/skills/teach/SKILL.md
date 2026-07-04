---
name: teach
description: Teach the user a new skill or concept, within this workspace.
---

Teach as a stateful workspace, not a one-off explanation. Use the current directory as the learning record.

## Workspace Files

- `MISSION.md` - why the user wants this topic; use [MISSION-FORMAT.md](MISSION-FORMAT.md).
- `RESOURCES.md` - trusted sources and communities; use [RESOURCES-FORMAT.md](RESOURCES-FORMAT.md).
- `reference/*.html` - compressed quick-reference documents.
- `learning-records/*.md` - numbered durable lessons learned; use [LEARNING-RECORD-FORMAT.md](LEARNING-RECORD-FORMAT.md).
- `lessons/*.html` - one self-contained lesson per file.
- `assets/*` - reusable lesson components.
- `NOTES.md` - user teaching preferences and working notes.

## Process

1. **Load state.** Read the mission, resources, notes, existing learning records, references, lessons, and assets that bear on the requested topic. If `MISSION.md` is missing or vague, ask why the user wants to learn this before teaching.
2. **Ground claims.** Use high-trust sources from `RESOURCES.md`; add missing primary sources before teaching facts. Do not rely on parametric memory for claims the user may later act on.
3. **Pick one lesson target.** Teach one skill or concept that fits the mission and the user's zone of proximal development. If the user did not name the target, infer it from learning records and mission.
4. **Create or update assets first.** Reuse `assets/*`. Add a shared stylesheet if none exists. Put reusable quiz widgets, simulators, diagrams, or CSS in `assets/`, not inline in a single lesson.
5. **Write the lesson.** Save `lessons/NNNN-<dash-case-name>.html`. Keep it short, clean, and printable. Include:
   - the minimum knowledge needed for the target skill,
   - an immediate practice loop with feedback,
   - retrieval practice for storage strength,
   - links to relevant lessons and references,
   - citations to trusted sources,
   - a prompt to ask follow-up questions.
6. **Update references.** Add or refresh `reference/*.html` for durable cheat sheets, algorithms, glossaries, syntax, poses, routines, or other reusable knowledge. Glossary terms become the vocabulary for later lessons.
7. **Record learning.** Add `learning-records/NNNN-<dash-case-name>.md` for non-obvious insights, mission changes, or durable corrections. Confirm with the user before changing the mission.
8. **Open the lesson when possible.** Use a local command or browser if available, then report the lesson path.

## Lesson Rules

- Keep each lesson tied to the mission and one tangible win.
- Separate knowledge from skill: make knowledge easy to acquire, then make skill practice effortful.
- Use desirable difficulty: retrieval, spacing, and interleaving only where they support the current skill.
- Make quiz answer options similar in length so formatting does not leak the answer.
- Route wisdom questions to real-world practice: answer what you can, then recommend high-reputation communities unless the user opts out.
