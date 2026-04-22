---
name: game-performance
description: Game performance optimization for Cocos Creator, Unity, mobile, WebGL, and real-time rendering. Use when diagnosing FPS drops, memory spikes, draw calls, GC allocations, loading time, physics cost, animation overhead, or runtime stutter.
---

# Game Performance

Chinese version: see `README.zh.md`.

## Trigger

Use this skill when the user asks for:

- game performance optimization
- FPS drop diagnosis
- mobile stutter
- Cocos Creator optimization
- Unity optimization
- draw call reduction
- memory leak investigation
- asset size reduction
- GC allocation reduction

## Source References

Verified accessible on 2026-04-22:

- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/performance-optimizer
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/performance-profiling
- https://github.com/sickn33/antigravity-awesome-skills/tree/main/skills/application-performance-performance-optimization

Provenance note: this skill is an original consolidation for this repository. The links above are reference paths for ecosystem conventions and adjacent skill ideas, not bulk verbatim copies.

## Optimization Rule

Measure first, then change. In games, the visible symptom may come from CPU scripting, GPU overdraw, texture upload, GC, physics, UI layout rebuild, shader compilation, logging, or asset loading.

## Profiling Workflow

1. Reproduce the issue in a controlled scene.
2. Capture baseline: FPS, frame time, CPU, GPU, memory, draw calls, batches, triangles, texture memory, and GC.
3. Classify the bottleneck.
4. Make one optimization at a time.
5. Compare before and after on the same device class.
6. Keep only changes that improve measured results enough to justify their complexity.

## Cocos Creator Optimization

- Reduce draw calls with atlas packing, material reuse, and batch-friendly node order.
- Avoid changing material, blend mode, stencil, mask, and texture in dense UI lists.
- Pool repeated dynamic nodes.
- Stop tweens and scheduled callbacks when nodes are disabled, pooled, or destroyed.
- Avoid frequent layout rebuilds on large hierarchies.
- Keep `update(dt)` free of repeated `getComponent` and hierarchy searches.
- Use event-driven UI updates where possible.
- Compress textures per target platform.

## Unity Optimization

- Use Profiler, Frame Debugger, Memory Profiler, and device builds.
- Avoid per-frame allocations.
- Pool frequently spawned objects.
- Use static batching, dynamic batching, GPU instancing, or SRP batching where appropriate.
- Split dynamic UI from static UI to reduce Canvas rebuilds.
- Reduce transparent overdraw.
- Spread expensive AI/pathfinding work across frames.

## Hot Path Rules

- Do not allocate arrays, closures, strings, or objects every frame.
- Do not scan scene hierarchies in hot paths.
- Cache references and invalidate caches explicitly.
- Avoid repeated sorting.
- Use spatial partitioning for many moving objects.
- Prefer stable frame pacing over occasional high FPS.
