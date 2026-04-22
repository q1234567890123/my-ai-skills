---
name: ai-prompt-enhance
description: Prompt engineering and precise instruction design for AI agents, coding tasks, research tasks, image/video prompts, reusable workflows, system instructions, and ambiguity reduction.
---

# AI Prompt Enhance

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks to:

- improve a prompt
- write precise AI instructions
- create system prompts
- design agent workflows
- reduce ambiguity
- generate image/video prompts
- convert vague tasks into executable prompts

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/prompt-engineering-patterns
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/ai-engineering-toolkit
- https://github.com/repowise-dev/claude-code-prompts
- https://github.com/wshobson/agents/blob/main/docs/agent-skills.md

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent prompt/agent skill ideas, not bulk verbatim copies.

## Core Rule

A good prompt reduces degrees of freedom where mistakes are costly and leaves freedom where judgment matters.

## Prompt Anatomy

- Role
- Goal
- Context
- Inputs
- Rules
- Process
- Output format
- Quality bar

## Upgrade Workflow

1. Extract the real task.
2. Identify ambiguity.
3. Decide fixed constraints vs flexible judgment.
4. Rewrite with clear sections.
5. Add examples only when they reduce ambiguity.
6. Add negative instructions only for likely failure modes.
7. Add a verification checklist.

## Output Template

```text
Role:
Goal:
Context:
Inputs:
Rules:
Process:
Output Format:
Quality Check:
```

