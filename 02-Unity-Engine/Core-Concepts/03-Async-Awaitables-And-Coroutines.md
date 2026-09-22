---
tags:
  - unity/async
  - unity/awaitable
date_created: 2026-09-22
aliases:
  - Unity 6 Awaitable
  - Async Programming
---

# ⏳ Asynchronous Programming: Coroutines vs. Unity 6 Awaitable

Unity 6 introduces native `Awaitable` support, replacing legacy Coroutines with zero-allocation, thread-safe async execution integrated directly into the C# task system.

---

## 1. Feature Comparison Matrix

| Feature | Coroutines (`IEnumerator`) | `Awaitable` (Unity 6+) |
| :--- | :--- | :--- |
| **Return Values** | Cannot return values directly | Supports direct typed return values (`Awaitable<T>`) |
| **Heap Allocation** | Allocates `YieldInstruction` objects | Zero allocation when integrated with engine loops |
| **Error Handling** | `try-catch` blocks unsupported inside yield | Native C# `try-catch-finally` support |
| **Cancellation** | Handled via `StopCoroutine()` | Handled natively via `CancellationToken` |

---


## 2. Unity 6 Awaitable Code Example

```csharp
using System.Threading;
using UnityEngine;

public class AsyncDataLoader : MonoBehaviour
{
    private async void Start()
    {
        try
        {
            Texture2D texture = await LoadRemoteTextureAsync("[https://api.game.com/asset](https://api.game.com/asset)", destroyCancellationToken);
            Debug.Log("Asset successfully loaded into memory!");
        }
        catch (System.OperationCanceledException)
        {
            Debug.Log("Task canceled upon GameObject destruction.");
        }
    }

    private async Awaitable<Texture2D> LoadRemoteTextureAsync(string url, CancellationToken cancellationToken)
    {
        await Awaitable.WaitForSecondsAsync(1.5f, cancellationToken);
        return new Texture2D(256, 256);
    }
}
````

## 🔗 Related Vault Notes

- [[02-Unity-Engine/Core-Concepts/02-MonoBehaviour-Lifecycle|MonoBehaviour Lifecycle]]
    
- [[01-CSharp-Basics/03-Memory-Management-and-GC|Memory Management]]