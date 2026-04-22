---
name: debug-pro
description: Professional debugging and root-cause localization workflow for crashes, regressions, flaky tests, build failures, performance bugs, integration issues, incorrect behavior, and unknown software failures.
---

# Debug Pro

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks to:

- debug a bug
- locate root cause
- fix a crash
- investigate a regression
- analyze logs
- repair failing tests
- diagnose performance bugs
- explain an error
- isolate integration failures

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/systematic-debugging
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/error-handling-patterns
- https://github.com/sickn33/antigravity-awesome-skills/blob/main/CATALOG.md

Path to watch in the catalog: `error-detective`.

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent debugging skill ideas, not bulk verbatim copies.

## Core Rule

Debugging is evidence management. Do not guess, thrash, or rewrite unrelated code. Form a hypothesis, find the cheapest observation that can disprove it, and narrow the search.

## Workflow

1. Reproduce the failure.
2. Capture exact symptom.
3. Define expected vs actual behavior.
4. Identify recent changes and dependency boundaries.
5. Build a hypothesis tree.
6. Test the highest-probability branch.
7. Patch the root cause, not the symptom.
8. Add regression coverage when practical.
9. Verify the failing case and nearby cases.

## Common Root Causes

- null or undefined state
- race condition
- off-by-one
- coordinate-space mismatch
- stale cache
- lifecycle ordering error
- duplicate event listener
- schema mismatch
- timezone or locale issue
- dependency version drift
- swallowed error

## Report Template

- Symptom:
- Expected:
- Reproduction:
- Evidence:
- Root cause:
- Fix:
- Verification:
- Remaining risk:
