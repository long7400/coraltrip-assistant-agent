---
name: codebase-design
description: Deep-module design vocabulary. Use for module/interface/seam design, testability, architecture deepening, or when another skill needs that vocabulary.
---

# Codebase Design

Use this vocabulary when designing or restructuring code. Aim for **deep modules**: substantial behavior behind a small interface, placed at a clean seam, testable through that interface.

## Glossary

Use these terms exactly; avoid overloaded substitutes like component, service, API, and boundary.

**Module** — anything with an interface and implementation: function, class, package, or tier-spanning slice.

**Interface** — everything a caller must know: signature, invariants, ordering, errors, config, and performance.

**Implementation** — what sits inside the module. Say adapter only when discussing the thing plugged into a seam.

**Depth** — behavior reachable per unit of interface. Deep modules hide much behind little; shallow modules expose nearly as much complexity as they contain.

**Seam** — the place where behavior can be changed without editing that place; the location where the interface lives.

**Adapter** — a concrete thing satisfying an interface at a seam. It names role, not internal substance.

**Leverage** — caller benefit from depth: more capability per concept learned.

**Locality** — maintainer benefit from depth: change, bugs, knowledge, and verification concentrate in one place.

## Checks

- **Deletion test**: if deleting the module removes complexity, it was likely pass-through; if complexity reappears across callers, it was earning depth.
- **Interface as test surface**: callers and tests cross the same seam. If tests must reach past the interface, reconsider the module shape.
- **Adapter count**: one adapter is hypothetical variation; two adapters make the seam real.
- **Surface area**: reduce methods and parameters before adding new seams.
- **Dependency direction**: accept dependencies at the seam; avoid creating hard-coded dependencies inside code that needs testing.

## Design Prompt

When planning a module or refactor, record:

- module boundary,
- public interface callers/tests depend on,
- hidden implementation details,
- seam placement and adapter strategy,
- highest useful test seam,
- why this is deeper than the current shape.

## Relationship Model

- A **Module** has exactly one **Interface** (the surface it presents to callers and tests).
- **Depth** is a property of a **Module**, measured against its **Interface**.
- A **Seam** is where a **Module**'s **Interface** lives.
- An **Adapter** sits at a **Seam** and satisfies the **Interface**.
- **Depth** produces **Leverage** for callers and **Locality** for maintainers.

## Rejected framings

- **Depth as line-count ratio**: rewards padding. Use depth-as-leverage.
- **Interface as only a language keyword or public methods**: too narrow; interface is every fact a caller must know.
- **"Boundary"**: overloaded with DDD's bounded context. Say **seam** or **interface**.

## Going deeper

- **Deepening a cluster given its dependencies** — see [DEEPENING.md](DEEPENING.md): dependency categories, seam discipline, and replace-don't-layer testing.
- **Exploring alternative interfaces** — see [DESIGN-IT-TWICE.md](DESIGN-IT-TWICE.md): spin up parallel sub-agents to design the interface several radically different ways, then compare on depth, locality, and seam placement.
