# Unity Client Review Checklist

## Correctness

- Event subscriptions are removed in `OnDisable` or `OnDestroy`.
- Async operations have cancellation tied to object lifetime.
- Scene transitions do not leave stale references or duplicate managers.
- Serialized fields are validated or fail clearly.
- Gameplay state has one clear owner.

## Performance

- No avoidable allocation in hot paths.
- Avoid LINQ, boxing, string formatting, and new collections in per-frame logic.
- Pool frequently spawned objects when spikes matter.
- UI updates avoid unnecessary layout rebuilds.
- Addressables assets are released when no longer needed.

## Architecture

- MonoBehaviours coordinate Unity lifecycle and scene wiring.
- Plain C# classes hold reusable domain logic where useful.
- ScriptableObjects are used deliberately and not mutated unexpectedly at runtime.
- Prefab dependencies are visible and easy to inspect.

## Verification

- Play Mode smoke test for lifecycle and scene transitions.
- Profiler check for GC Alloc and spikes.
- Device or target-quality test for mobile-sensitive changes.
- Regression check for UI, input, save/load, and asset loading paths.
