---
tags:
  - unity/physics
  - unity/components
date_created: 2026-09-22
aliases:
  - Unity Physics API
  - Rigidbody & Raycasting
---

# 🧲 Physics Engine, Rigidbodies, and Colliders

Unity's 3D physics relies on NVIDIA PhysX, while 2D physics uses Box2D. Understanding collision detection modes and non-allocating query APIs prevents physics glitches and performance bottlenecks.

---


## 1. Collision Detection Modes

* **Discrete:** Default mode. Checks collisions once per fixed timestep. Can suffer from "tunneling" with high-speed objects.
* **Continuous:** Used for fast-moving dynamic objects colliding with static mesh colliders.
* **Continuous Dynamic:** Used for fast-moving dynamic objects colliding with other dynamic objects.

---


## 2. Zero-Allocation Raycasting

Avoid standard `Physics.RaycastAll()` which allocates array memory on the heap every call. Use `RaycastNonAlloc()` with pre-allocated buffers.

```csharp
using UnityEngine;

public class PhysicsSensor : MonoBehaviour
{
    private readonly RaycastHit[] _hitBuffer = new RaycastHit[10];

    public int ScanEnvironment(Vector3 direction, float distance)
    {
        int hitCount = Physics.RaycastNonAlloc(transform.position, direction, _hitBuffer, distance);
        for (int i = 0; i < hitCount; i++)
        {
            Debug.Log($"Hit object: {_hitBuffer[i].collider.name}");
        }
        return hitCount;
    }
}
````

## 🔗 Related Vault Notes

- [[02-Unity-Engine/Core-Concepts/02-MonoBehaviour-Lifecycle|MonoBehaviour Lifecycle]]
    
- [[01-CSharp-Basics/03-Memory-Management-and-GC|Memory Management]]