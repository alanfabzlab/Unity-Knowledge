---
tags:
  - unity/lifecycle
  - unity/monobehaviour
date_created: 2026-09-22
aliases:
  - Execution Order
  - MonoBehaviour Lifecycle
---

# 🔄 MonoBehaviour Lifecycle & Execution Order

The exact sequence in which Unity engine event functions execute determines system initialization, physics loops, frame updates, and cleanup routines.

---

## 1. Lifecycle Execution Diagram

```text
 Initialization
 ├── Awake()         -> Executed when script instance is loaded.
 ├── OnEnable()      -> Executed when GameObject/Component is activated.
 └── Start()         -> Executed before first frame update (if enabled).
 Physics Loop (Fixed Timestep: e.g., 0.02s)
 ├── FixedUpdate()   -> Deterministic physics calculations.
 ├── OnTrigger/Collision -> Physics engine event resolution.
 └── yield WaitForFixedUpdate
 Input & Game Logic (Variable Timestep / Per Frame)
 ├── Update()        -> Gameplay logic, input handling, timer tracking.
 ├── LateUpdate()    -> Executed after Update (Camera follow, IK resolution).
 Render & GUI
 └── OnGUI()         -> Legacy GUI rendering loop.
 Deconstruction
 ├── OnDisable()     -> Called when deactivated.
 └── OnDestroy()     -> Called before object removal from scene memory.
````

## 2. Key Lifecycle Distinctions

|**Lifecycle Method**|**Frequency**|**Primary Responsibility**|**Delta Time Parameter**|
|---|---|---|---|
|**`Awake()`**|Once on Init|Internal variable setup, component caching (`GetComponent<T>`)|N/A|
|**`Start()`**|Once on Enable|Cross-object references, dependency handshake|N/A|
|**`FixedUpdate()`**|Deterministic (50Hz default)|Rigidbody forces, character controller movement|`Time.fixedDeltaTime`|
|**`Update()`**|Frame-rate dependent|Reading user input, non-physics movement, state checks|`Time.deltaTime`|
|**`LateUpdate()`**|Frame-rate dependent|Camera transforms, bone transformations, procedural animation|`Time.deltaTime`|

## 3. Modern Asynchronous Workflows (Unity 6 Awaitable)

Replacing legacy Coroutines with high-performance native `Awaitable` functions eliminates delegate allocations and supports async C# patterns natively.


```csharp
using UnityEngine;

public class AsyncLifecycleExample : MonoBehaviour
{
    private async void Start()
    {
        await Awaitable.WaitForSecondsAsync(2.0f, destroyCancellationToken);
        Debug.Log("Executed 2 seconds later without GC allocation!");
    }
}
```

## 🔗 Related Vault Notes

- [[02-Unity-Engine/Core-Concepts/01-Unity-Ecosystem-Overview|Unity Ecosystem Overview]]
    
- [[03-Game-Architecture/01-ScriptableObject-Architecture|ScriptableObject Architecture]]