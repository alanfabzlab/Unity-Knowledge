---
tags:
  - unity/code-snippet
  - design-patterns
  - singleton
date_created: 2026-09-22
aliases:
  - Generic Singleton
  - Persistent Singleton
---

# 🔒 Production Generic Persistent Singleton

A thread-safe, robust generic Singleton implementation for persistent manager classes (`AudioManager`, `GameManager`) that survive scene transitions.

---

## 1. Generic Persistent Singleton Implementation

```csharp
using UnityEngine;

public abstract class PersistentSingleton<T> : MonoBehaviour where T : MonoBehaviour
{
    public static T Instance { get; private set; }

    protected virtual void Awake()
    {
        if (Instance != null && Instance != this)
        {
            Destroy(gameObject);
            return;
        }

        Instance = this as T;
        DontDestroyOnLoad(gameObject);
    }
}
````

## 2. Usage Example


```csharp
public class AudioManager : PersistentSingleton<AudioManager>
{
    public void PlaySoundEffect(AudioClip clip)
    {
        // Sound execution logic
    }
}

// Global invocation anywhere in code:
// AudioManager.Instance.PlaySoundEffect(clip);
```

## 🔗 Related Vault Notes

- [[02-Unity-Engine/Core-Concepts/02-MonoBehaviour-Lifecycle|MonoBehaviour Lifecycle]]
    
- [[04-Snippets-And-Scripts/02-Object-Pooling|Object Pooling Pattern]]