---
name: game-coding
description: Game development coding standards for Cocos Creator, Unity, and general gameplay systems. Use when implementing gameplay, input handling, UI interaction, level flow, animation hooks, entity state, game controllers, or engine lifecycle code.
---

# Game Coding

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks for:

- gameplay implementation
- Cocos Creator code
- Unity code
- input handling
- UI interaction
- level logic
- animation event wiring
- game state management
- game architecture review

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/godot-gdscript-patterns
- https://github.com/sickn33/antigravity-awesome-skills/blob/main/CATALOG.md

Paths to watch in the catalog: `game-development/multiplayer`, `godot-gdscript-patterns`.

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent skill ideas, not bulk verbatim copies.

## Core Design Rule

Separate game rules from presentation. The gameplay state should be deterministic, inspectable, and testable. Engine nodes, prefabs, cameras, tweens, particles, and sounds should present or trigger state, not secretly own the rules.

## Layering

- Core: rules, state transitions, scoring, win/lose checks, random seed logic.
- View: nodes, transforms, sprites, animation, particles, input components.
- Orchestration: scene loading, save/load, SDKs, ads, analytics, platform services.

## Cocos Creator Rules

1. Bind touch events to visible nodes with `UITransform` and render components.
2. Do not change node parent between touch start and touch end.
3. Keep node layer and camera visibility aligned.
4. Keep `Canvas.cameraComponent` valid.
5. Avoid dynamic full-screen `BlockInputEvents` masks unless the project has a safe established pattern.
6. Reuse nodes with pools for frequent spawn/despawn effects.
7. Stop tweens and scheduled callbacks when disabling, pooling, or destroying nodes.

## Unity Rules

1. Keep `Update()` small.
2. Cache frequently used component references.
3. Use object pools for projectiles, VFX, floating text, and repeated UI items.
4. Avoid `FindObjectOfType`, `GameObject.Find`, and tag searches in hot paths.
5. Keep physics changes in `FixedUpdate` or explicit simulation steps.
6. Use ScriptableObjects for stable configuration when appropriate.

## Gameplay Safety Checklist

- Can input be triggered twice?
- Can animation callbacks fire after a node/object is gone?
- Can level-clear or fail logic run more than once?
- Are scene reload and pause/resume handled?
- Does pooled state reset listeners, parent, scale, alpha, layer, and animation?
- Are SDK reward flows confirmed before changing gameplay state?
