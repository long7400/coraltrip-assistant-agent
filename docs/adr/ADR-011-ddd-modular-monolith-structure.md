# ADR-011: DDD Modular Monolith Structure

## Status

Accepted

## Date

2026-07-05

## Context

CoralTrip Assistant Agent targets a modular platform architecture. The product and technical source documents require DDD, hexagonal boundaries, a strict Supplier Adapter Layer, controlled AI tool execution, auditable booking/payment/finance flows, and compliance-by-design.

The repository is currently a thin Java/Maven skeleton. Starting with microservices would add distributed complexity before the domain model, seams, tests, and operational evidence are mature enough.

The structure must avoid duplicate runtime entrypoints. Internal modules may expose ports and adapters, but they must not define their own `main` classes until a later ADR accepts a service split.

## Decision

Use a Maven workspace with one runnable application and internal DDD modules:

- `apps/coraltrip-app` is the only application entrypoint for the current modular monolith.
- `modules/core` owns identity, privacy, catalog, availability, booking, payment, finance, and ops.
- `modules/ai-agent` owns AI conversation, planning, RAG, Tool Gateway, MCP, guardrails, memory, and evaluation.
- `modules/supplier-adapter` owns supplier/provider integration and provider-specific mapping.
- `modules/workflow`, `modules/notification`, and `modules/search` own async workflows, notification delivery, and search projections inside the same deployable application for now.
- `libs/shared-kernel` contains small cross-context primitives only.
- Platform libraries contain cross-cutting security, observability, and test support.

Each bounded context follows a hexagonal layout:

```text
context/
  domain/
  application/
  ports/
  adapters/
  config/
```

Domain code must not depend on Spring, JPA, supplier SDKs, payment SDKs, or AI provider SDKs. External systems enter through ports and adapters.

## Consequences

- This is not microservice-first. Folder and Maven module boundaries are not network boundaries.
- There is one startup class until a future ADR accepts a service split.
- Duplicate-check invariant: the repository should have one `*Application.java` startup class and one application-level `application.yml` while it remains a single deployable modular monolith.
- The application can evolve as a modular monolith while preserving seams that can be split later if scale, team ownership, deployment cadence, or security isolation requires it.
- Provider-specific details stay inside `modules/supplier-adapter`.
- AI cannot mutate booking/payment/finance state directly; it must go through Tool Gateway and application ports.
- Future implementation issues should add aggregates, invariants, domain events, ports, adapter contracts, and tests inside these boundaries rather than creating global controller/service/repository layers.
