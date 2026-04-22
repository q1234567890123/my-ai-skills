---
name: clean-code
description: Production clean-code guidance for maintainability, naming, modularity, refactoring, tests, error handling, and long-term code quality. Use when improving code structure, reviewing code quality, or making software easier to understand and safely change.
---

# Clean Code

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks for:

- clean code
- maintainable code
- naming improvement
- refactoring
- SOLID or modular design
- testability
- error handling
- code review for quality

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/code-refactoring-refactor-clean
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/error-handling-patterns

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent skill ideas, not bulk verbatim copies.

## Clean Code Rules

1. Make names reveal intent.
2. Keep functions focused on one level of abstraction.
3. Keep modules cohesive and public APIs narrow.
4. Separate domain logic from IO, UI, storage, and transport when practical.
5. Make side effects explicit.
6. Prefer simple composition over inheritance.
7. Validate inputs at trust boundaries.
8. Make failure modes observable.
9. Write tests around behavior that matters.
10. Stop refactoring when the code is clearly better and the risk starts rising.

## Naming

- Use verbs for functions.
- Use predicates for booleans.
- Include units in names: `timeoutMs`, `widthPx`, `priceCents`.
- Avoid vague buckets such as `data`, `info`, `helper`, `manager`, or `utils` unless they are established local terms.

## Refactoring Workflow

1. Define behavior that must not change.
2. Add or locate a test around that behavior.
3. Make one structural change at a time.
4. Run verification after meaningful steps.
5. Keep changes scoped to the requested area.

## Review Checklist

- Is the responsibility boundary clear?
- Is there repeated conditional logic that should live in one owner?
- Does the code mix validation, transformation, persistence, and rendering?
- Are errors swallowed?
- Are tests tied to implementation details?
- Did the change introduce unnecessary concepts?
