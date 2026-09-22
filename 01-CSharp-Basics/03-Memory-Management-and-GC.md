---
tags:
  - csharp/memory
  - unity/performance
  - garbage-collection
date_created: 2026-09-22
aliases:
  - C# Memory Management
  - GC Optimization
---

# 🧠 C# Memory Management & Garbage Collection in Unity

Understanding C# heap allocations and Garbage Collection (GC) behavior is critical to preventing frame drops and micro-stuttering in Unity applications.

---

## 1. Stack vs. Heap Allocation

* **Stack Memory:**
  * Stores value types (`int`, `float`, `bool`, `struct`, `Vector3`).
  * Managed automatically via CPU stack frame pushes and pops.
  * Zero GC overhead, ultra-fast allocation and deallocation.
* **Managed Heap:**
  * Stores reference types (`class`, `string`, array, `Delegate`, `closure`).
  * Tracked by Unity’s C# Garbage Collector (Boehm-Demers-Weiser GC in Mono/IL2CPP).
  * Allocations persist until garbage collection sweeps unused references.

---

## 2. Common Garbage Generation Sources in Unity

### A. String Concatenation
Strings are immutable reference types. Concatenating strings in `Update()` creates temporary allocations on every frame.
```csharp
// ❌ BAD: Allocates new string every frame
void Update() {
    scoreText.text = "Score: " + currentScore.ToString();
}

// ✅ GOOD: Use Cached StringBuilder or TextMeshPro formatting
void Update() {
    scoreText.SetText("Score: {0}", currentScore);
}
````

### B. Boxing & Unboxing

Occurs when casting a value type (`struct`, `int`) to an interface or object container.


```csharp
// ❌ BAD: Boxing struct to interface allocates on Heap
IEquatable<Vector3> point = transform.position; 

// ✅ GOOD: Pass concrete structs directly
Vector3 point = transform.position;
```

### C. Coroutines & Closures

Instantiating `new WaitForSeconds()` or passing local variables into lambdas allocates heap objects.


```csharp
// ❌ BAD: Allocates new instruction every invocation
IEnumerator HealRoutine() {
    yield return new WaitForSeconds(1.0f);
}

// ✅ GOOD: Cache YieldInstruction instances
private readonly WaitForSeconds _waitOneSecond = new WaitForSeconds(1.0f);
IEnumerator HealRoutine() {
    yield return _waitOneSecond;
}
```

## 3. Best Practices for GC Minimization

1. **Object Pooling:** Reuse `GameObject` instances instead of invoking `Instantiate()` and `Destroy()`.
    
2. **Collection Caching:** Avoid returning arrays from properties (e.g., `Input.touches` or `Physics.RaycastAll`). Pass pre-allocated `List<T>` or `Array` containers into `NonAlloc` methods (`Physics.RaycastNonAlloc`).
    
3. **Structs over Classes:** Use `struct` for small data containers without deep object hierarchies.
    

## 🔗 Related Vault Notes

- [[02-Unity-Engine/Core-Concepts/01-Unity-Ecosystem-Overview|Unity Ecosystem Overview]]
    
- [[04-Snippets-And-Scripts/02-Object-Pooling|Object Pooling Pattern]]
