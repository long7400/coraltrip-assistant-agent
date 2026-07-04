# CoralTrip Assistant Agent Context

This is the shared domain glossary for agents working in this repository. Use these terms in plans, issues, tests, modules, and architecture notes. Update this file when a term is resolved or corrected during planning.

## Source Documents

- `spec-prd/PRD_CoralTrip_Assistant_Agent_v2.0.md` is the current product requirements source.
- `spec-prd/SPEC_CoralTrip_Assistant_Agent_v2.0.md` is the current technical architecture source.
- `spec-prd/CoralTrip_Backlog_90pct_v2.1.md` and `.xlsx` contain backlog/story material.

## Product Language

**WCPCT**:
Weekly Contribution-Positive Confirmed Trips. The North Star metric. A trip counts only when it is confirmed or ticketed, has valid payment or B2B debt confirmation, is not under open refund/fraud/cancellation risk, has positive contribution margin, and includes meaningful AI or decision-support involvement.
Avoid: raw booking count, gross trip count.

**Trip**:
A customer travel purchase or itinerary unit that can include tour package, flight, hotel, car/transfer, booking operations, and AI-assisted planning.
Avoid: order when referring to the customer travel outcome; booking when referring to the broader travel experience.

**Booking lifecycle**:
The state path from draft to hold, payment, confirmed or ticketed, change, cancellation, refund, and completed. Booking lifecycle changes must be auditable and idempotent.
Avoid: ad hoc status updates.

**Supplier Adapter Layer**:
The mandatory abstraction between CoralTrip and external providers for tour, flight, hotel, car/transfer, payment, and notification integrations. Provider-specific APIs such as Amadeus, Booking.com, Agoda, VNPay, or MoMo must stay behind adapters.
Avoid: hard-coded provider integration in domain core.

**AI Concierge**:
The user-facing assistant experience for search, itinerary planning, policy explanation, comparison, quote generation, and assisted checkout.
Avoid: generic chatbot when the assistant can call tools or reason over CoralTrip policy/inventory.

**Tool Gateway**:
The controlled execution layer through which AI calls application tools. It enforces auth, confirmation, policy, audit, and rate limits before any sensitive action.
Avoid: direct AI mutation of booking, payment, or finance state.

**Policy Accuracy**:
The requirement that AI answers about cancellation, refund, visa, supplier terms, and operational rules match authoritative policy sources and pass evaluation.
Avoid: plausible but uncited policy explanations.

**Contribution Margin**:
Net revenue minus variable costs including payment fees, supplier commission, LLM cost, support cost, voucher/SMS/email cost, and refund reserve.
Avoid: gross transaction value as a profitability proxy.

## Architecture Language

**Modular platform**:
The target architecture style: modular monolith for domain core with service boundaries clear enough to split AI Agent, Supplier Adapter, Notification/Workflow, and related capabilities when needed.
Avoid: premature microservices that do not preserve domain seams.

**Module**:
Anything with an interface and implementation. A module can be a function, package, service, or cross-tier slice.
Avoid: component or service when the design question is really about interface and implementation.

**Interface**:
Everything a caller must know to use a module correctly: signatures, invariants, ordering constraints, error modes, configuration, performance, and side effects.
Avoid: API when only the type-level surface is meant.

**Seam**:
A deliberate place where implementation can vary behind a stable interface. Tests and adapters should attach at meaningful seams, not private internals.

**Adapter**:
An implementation behind a seam that translates between CoralTrip concepts and an external provider, datastore, transport, or tool.

## Agent Workflow Language

**Shared design concept**:
The human and agent's live agreement about what should be built and why. A PRD captures it after grilling, but the document is not a substitute for resolving uncertainty.
Avoid: treating a first draft plan as accepted truth.

**Tracer bullet**:
A narrow vertical slice that proves one useful path end-to-end through the product and integration layers. It should be independently verifiable and tied to user stories.
Avoid: horizontal slices such as all database work, all services, or all UI before behavior is demonstrable.

**Issue claim**:
The precise outcome an issue promises to deliver. If the claim requires a specific mechanism, do not substitute an adjacent mechanism without explicit user acceptance.
Avoid: vague task titles that cannot be verified.

**HITL**:
Human-in-the-loop work that requires active judgement: grilling, PRD shaping, issue breakdown, architecture decisions, compliance/policy tradeoffs, user-facing design judgement, and final acceptance.
Avoid: sending unresolved judgement work to an AFK agent.

**AFK**:
Away-from-keyboard delegated work. In this repo, AFK is only appropriate for approved, bounded implementation or review tasks with source material, acceptance criteria, and verification.
Avoid: unsupervised planning or ambiguous product decisions.

**Manual QA Issue**:
A HITL issue that captures human acceptance work after AFK slices: product feel, visual judgement, compliance judgement, or click-through verification that the repo cannot prove automatically.
Avoid: hiding manual acceptance inside an AFK implementation issue.

**Research artifact**:
A cited Markdown result from primary-source reading. It must feed a PRD, issue, ADR, or glossary update, or be marked superseded/deleted.
Avoid: stale markdown notes that no later agent is told to read.

**Prototype verdict**:
The durable answer from throwaway code: the question, observed result, accepted decision, and where that decision was folded back into the plan.
Avoid: keeping prototype code without a verdict.

**Instruction budget**:
The limited amount of steering an agent can reliably follow. Always-loaded instructions should stay compact and stable; detailed or situational guidance belongs in linked docs, skills, PRDs, issues, or ADRs.
Avoid: growing `AGENTS.md` with every preference, volatile file path, or one-off warning.

**Context pointer**:
A short always-visible reference that tells an agent when to load deeper material, such as a skill description pointing to `SKILL.md` or a `SKILL.md` link pointing to a reference file.
Avoid: burying required behavior behind a vague link.

**Procedure skill**:
A user-steered workflow skill with ordered steps and completion gates, such as grilling, PRD creation, issue splitting, implementation, review, or setup.
Avoid: treating unresolved human judgement as an implicitly invoked background ability.

**Ability skill**:
A shared vocabulary or capability skill that other skills may invoke for a reusable discipline, such as domain modeling or codebase design.
Avoid: duplicating the vocabulary in every procedure skill.

**Leading word**:
A compact term that carries a repeated workflow concept, such as grill, tracer bullet, tight loop, red, seam, AX, HITL, or AFK.
Avoid: restating the full definition each time the term appears.

**Agent Experience (AX)**:
How easy it is for an agent to work safely in the repo. AX includes typechecks, tests, formatters, linters, smoke checks, module shape, and clear seams.
Avoid: optimizing user-facing UX while leaving agents without feedback loops or navigable module boundaries.

## Open Questions

- The repo currently has a Java/Maven skeleton targeting Java 21. The SPEC targets Spring Boot/Spring AI architecture, but implementation dependencies are not yet aligned with that target.
- Issue tracking is configured as local markdown until a GitHub/GitLab/other tracker is explicitly chosen.
