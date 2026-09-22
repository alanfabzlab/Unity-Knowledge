---
tags:
  - unity/architecture
  - scriptable-objects
  - design-patterns
date_created: 2026-09-22
aliases:
  - ScriptableObject Data Flow
  - Modular Architecture
---

# 📐 ScriptableObject-Driven Game Architecture

ScriptableObjects (SOs) serve as data containers independent of `GameObject` instances. Utilizing ScriptableObjects reduces memory overhead, decouples code dependencies, and enables modular game architecture.

---

## 1. Core Architectural Uses

1. **Data Containers:** Storing game balance variables, item stats, and configuration files without attaching scripts to scene objects.
2. **Event Channels:** Decoupling systems via event-driven messaging (Publisher-Subscriber pattern).
3. **Runtime Sets:** Dynamic lists that track active scene objects (e.g., active enemies, objective markers) at runtime without `FindObjectsOfType<T>()`.

---

## 2. Implementations

### A. Game Event Channel Pattern
Decouples sender components (e.g., Player Health) from receiver components (e.g., UI Healthbar, Audio Manager).

```csharp
using UnityEngine;

[CreateAssetMenu(fileName = "VoidEventChannel", menuName = "Architecture/Events/Void Event Channel")]
public class VoidEventChannelSO : ScriptableObject
{
    private System.Action OnEventRaised;

    public void RaiseEvent()
    {
        OnEventRaised?.Invoke();
    }

    public void RegisterListener(System.Action listener)
    {
        OnEventRaised += listener;
    }

    public void UnregisterListener(System.Action listener)
    {
        OnEventRaised -= listener;
    }
}
````


### B. Shared Variables Pattern

Allows multiple prefabs and scripts to read/write a shared value without direct code dependencies.


```csharp
using UnityEngine;

[CreateAssetMenu(fileName = "FloatVariable", menuName = "Architecture/Variables/Float")]
public class FloatVariableSO : ScriptableObject
{
    [SerializeField] private float value;

    public float Value
    {
        get => value;
        set => this.value = value;
    }
}
```


## 3. Advantages vs. Disadvantages

|**Feature**|**ScriptableObject Architecture**|**Direct Component Referencing**|
|---|---|---|
|**Coupling**|Loosely Coupled|Tightly Coupled|
|**Scene Independence**|High (Assets persist across scene loads)|Low (Tied to scene lifecycle)|
|**Memory Footprint**|Shared single memory address for all instances|Duplicated field data per `GameObject`|
|**Runtime Mutation**|Modifies asset file directly in Editor (Requires reset strategies)|Resets upon exiting Play Mode|

## 🔗 Related Vault Notes

- [[01-CSharp-Basics/03-Memory-Management|Memory Management]]
    
- [[04-Snippets-And-Scripts/01-Singleton-Pattern|Singleton Pattern]]