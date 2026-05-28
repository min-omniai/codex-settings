---
name: unity-client-review
description: "Review Unity game client code and architecture for C# gameplay, MonoBehaviour lifecycle, ScriptableObject usage, Addressables, UI, input, async flows, memory, GC allocation, mobile performance, maintainability, and PR feedback. Use when asked to review Unity code, inspect a game client PR, find performance risks, or improve Unity client structure."
---

# Unity Client Review

## Review Order

1. Understand the feature intent, target platform, Unity version, and relevant packages if visible.
2. Check correctness first: lifecycle order, null paths, event timing, async cancellation, scene transitions, and state ownership.
3. Check Unity-specific risks: serialized references, prefab coupling, ScriptableObject mutation, Addressables load/release balance, input timing, UI rebuilds, and object lifetime.
4. Check performance: per-frame allocations, LINQ or closures in hot paths, Instantiate/Destroy spikes, texture or asset memory, draw calls, batching, and mobile constraints.
5. Check maintainability: responsibility boundaries, naming, testability, inspector ergonomics, and whether the code teaches future readers the right pattern.

## Response Format

Lead with findings ordered by severity. Use file and line references when available.

For each finding include:
- Problem
- Why it matters in Unity/game-client terms
- Suggested fix
- Test or verification step

If no serious issues are found, say that clearly and mention remaining risks or test gaps.

## Defaults

- Prefer practical fixes over broad refactors.
- Do not over-abstract small gameplay code.
- Treat Update, LateUpdate, FixedUpdate, UI callbacks, async continuations, and asset loading paths as higher-risk areas.
- For student or junior code, include concise teaching notes after the findings.
- For production PR review, keep the tone direct and prioritize defects, regressions, and missing validation.

## References

Read `references/review-checklist.md` when performing a broad review or when the code touches assets, UI, async, or performance-sensitive paths.
