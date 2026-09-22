---
tags:
  - csharp/events
  - unity/architecture
date_created: 2026-09-22
aliases:
  - Delegates and Actions
  - C# Events
---

# ⚡ Delegates, Actions, and C# Events

Delegates act as type-safe function pointers, enabling loose coupling between systems (e.g., UI updates triggered by gameplay events).

---


## 1. C# Events vs. UnityEvent

* **C# `System.Action` / `System.Func`:** High performance, zero allocations during invocation, managed strictly in C# code.
* **`UnityEngine.Events.UnityEvent`:** Inspector-bindable, useful for designer workflows, but introduces reflection overhead and small heap allocations.


```csharp
using System;
using UnityEngine;

public class PlayerHealth : MonoBehaviour
{
    // C# Event Pattern (Preferred for core game logic)
    public static event Action<float> OnHealthChanged;

    private float _currentHealth = 100f;

    public void ModifyHealth(float delta)
    {
        _currentHealth += delta;
        OnHealthChanged?.Invoke(_currentHealth);
    }
}
````


## 2. Memory Leak Prevention

Always unsubscribe from events when the subscribing component is disabled or destroyed to prevent dangling reference memory leaks.


```csharp
private void OnEnable()
{
    PlayerHealth.OnHealthChanged += UpdateHealthBar;
}

private void OnDisable()
{
    PlayerHealth.OnHealthChanged -= UpdateHealthBar;
}
```

## 🔗 Related Vault Notes

- [[03-Game-Architecture/01-ScriptableObject-Architecture|ScriptableObject Architecture]]
    
- [[01-CSharp-Basics/03-Memory-Management-and-GC|Memory Management & GC]]