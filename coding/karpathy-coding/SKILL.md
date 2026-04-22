---
name: karpathy-coding
description: Minimalist, high-signal coding discipline for AI-assisted programming. Use when writing, reviewing, simplifying, or refactoring code with a focus on clear data flow, small functions, local reasoning, testable behavior, and removal of unnecessary abstraction.
---

# Karpathy Coding

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks for:

- Karpathy-style coding
- simple and readable implementation
- reducing abstraction
- refactoring messy code
- reviewing AI-generated code
- making code smaller, more obvious, and easier to debug

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/andrej-karpathy
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/code-refactoring-refactor-clean
- https://github.com/iliaal/ai-skills

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent skill ideas, not bulk verbatim copies.

## Core Rules

1. Read existing code before editing.
2. Prefer the simplest working design.
3. Use plain data structures and direct control flow.
4. Add abstraction only when it removes real duplication or complexity.
5. Keep state ownership obvious.
6. Use guard clauses to avoid deep nesting.
7. Keep functions short enough to understand in one pass.
8. Name variables by intent, not implementation trivia.
9. Validate at boundaries and fail with useful context.
10. Test behavior, not private implementation details.

## AI Coding Discipline

When acting as an AI coding agent:

- Do not start with a large architecture proposal when a narrow patch is enough.
- Do not rewrite unrelated code for style.
- Do not introduce a framework, registry, event bus, base class, or plugin layer unless the codebase already uses that pattern or the need is proven.
- Do not leave TODO placeholders in executable paths.
- Do not claim completion before running the relevant verification.
- Do not hide uncertainty. State what was verified and what was not.

## Implementation Workflow

1. Identify the exact behavior requested.
2. Locate the smallest owner module.
3. Read surrounding code and tests.
4. Make the smallest coherent change.
5. Run type checks, tests, or the closest available validation.
6. Re-read the diff and delete unnecessary code.

## Quality Checklist

- Can another engineer understand the data flow without asking you?
- Is every new abstraction paying rent?
- Are side effects visible?
- Are error paths explicit?
- Are tests focused on the behavior users or callers rely on?
- Did the patch avoid unrelated churn?

