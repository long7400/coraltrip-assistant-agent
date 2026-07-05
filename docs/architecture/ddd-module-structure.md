# DDD Module Structure

CoralTrip Assistant Agent is structured as a single-start modular monolith. Maven modules are code and dependency boundaries, not microservice or network boundaries.

## Runtime Entry

```text
apps/
  coraltrip-app/
    src/main/java/com/coraltrip/CoralTripAssistantApplication.java
    src/main/resources/application.yml
```

`apps/coraltrip-app` is the only runnable application. Internal modules must not add their own startup classes unless a later ADR accepts a microservice or separate worker split.

## Internal Modules

```text
modules/
  core/
  ai-agent/
  supplier-adapter/
  workflow/
  notification/
  search/

libs/
  shared-kernel/
  platform-security/
  platform-observability/
  test-support/
```

- `modules/core` owns the main business bounded contexts: identity, privacy, catalog, availability, booking, payment, finance, and ops.
- `modules/ai-agent` owns conversation, planning, RAG, Tool Gateway, MCP, guardrails, memory, and evaluation.
- `modules/supplier-adapter` owns provider-specific mapping and adapter implementation.
- `modules/workflow`, `modules/notification`, and `modules/search` are internal modules for async orchestration, delivery, and projections.
- `libs/shared-kernel` should stay small: IDs, money, time, errors, events, request context, and pagination.

## Context Layout

Bounded contexts use this hexagonal layout:

```text
context/
  domain/
  application/
  ports/
    in/
    out/
  adapters/
    in/
    out/
  config/
```

Domain code must stay free of Spring, JPA, supplier SDKs, payment SDKs, and AI provider SDKs. External systems enter through ports and adapters.

## Duplicate Check

The current single-deployable invariant is:

- exactly one `*Application.java`,
- exactly one application-level `application.yml`,
- no `main` class in `modules/`,
- provider-specific code only inside `modules/supplier-adapter`.
