---
name: tdd
description: Test-driven development. Use when the user wants to build features or fix bugs test-first, mentions "red-green-refactor", or wants integration tests.
---

# Test-Driven Development

Run red-green-refactor at agreed seams. Use this skill before and during each cycle, not as a cleanup pass after implementation.

When exploring the codebase, read `CONTEXT.md` (if it exists) so test names and interface vocabulary match the project's domain language, and respect ADRs in the area you're touching.

## What a good test is

Tests verify behavior through public interfaces, not implementation details. A good test reads like a specification and survives refactors.

See [tests.md](tests.md) for examples and [mocking.md](mocking.md) for mocking guidelines.

## Seams — where tests go

Tests live at public seams: the interface where behavior is observable without reaching inside.

Before writing any test, write down the seam under test and confirm it with the user. Ask: "What's the public interface, and which seams should we test?"

## Anti-patterns

- **Implementation-coupled** — mocks internals, tests private methods, or verifies through side channels.
- **Tautological** — expected values are recomputed the same way as the implementation. Use known-good literals, worked examples, or the spec.
- **Horizontal slicing** — all tests first, then all implementation. Work vertically: one test, one implementation, repeat.

## Rules of the loop

- **Red before green.** Write the failing test first, then only enough code to pass it.
- **One slice at a time.** One seam, one test, one minimal implementation per cycle.
- **Refactor only after green.** Keep same-slice cleanup small and prove the test stays green. Broader coding-standards cleanup belongs to `$code-review`, where a fresh reviewer can inspect the diff without overloading implementation.
