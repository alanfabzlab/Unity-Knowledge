---
tags:
  - unity/code-snippet
  - design-patterns
  - object-pooling
date_created: 2026-09-22
aliases:
  - Object Pooling
  - Performance Snippets
---

# 📦 Production-Ready Object Pooling Pattern

Object pooling eliminates garbage collection spikes caused by frequent `Instantiate()` and `Destroy()` operations by reusing inactive `GameObject` instances.

---


## 1. Unity Built-in ObjectPool (`UnityEngine.Pool`)

Unity provides a native, highly optimized `ObjectPool<T>` class starting from Unity 2021.

```csharp
using UnityEngine;
using UnityEngine.Pool;

public class BulletSpawner : MonoBehaviour
{
    [SerializeField] private GameObject bulletPrefab;
    private IObjectPool<GameObject> _bulletPool;

    private void Awake()
    {
        _bulletPool = new ObjectPool<GameObject>(
            createFunc: CreateBullet,
            actionOnGet: OnGetBullet,
            actionOnRelease: OnReleaseBullet,
            actionOnDestroy: OnDestroyBullet,
            collectionCheck: true,
            defaultCapacity: 20,
            maxSize: 100
        );
    }

    private GameObject CreateBullet()
    {
        GameObject bullet = Instantiate(bulletPrefab);
        return bullet;
    }

    private void OnGetBullet(GameObject bullet)
    {
        bullet.SetActive(true);
    }

    private void OnReleaseBullet(GameObject bullet)
    {
        bullet.SetActive(false);
    }

    private void OnDestroyBullet(GameObject bullet)
    {
        Destroy(bullet);
    }

    public GameObject SpawnBullet()
    {
        return _bulletPool.Get();
    }

    public void DespawnBullet(GameObject bullet)
    {
        _bulletPool.Release(bullet);
    }
}
````


## 2. Key Rules for Object Pooling

1. **Reset State on Get:** Ensure health, position, velocity, and visual trail renderers are reset in `OnGet` before displaying the object.
    
2. **Avoid Oversizing Default Capacity:** Allocate a reasonable baseline (`defaultCapacity`) based on average active screen entities to avoid wasting memory.
    

## 🔗 Related Vault Notes

- [[01-CSharp-Basics/03-Memory-Management|Memory Management & GC]]
    
- [[02-Unity-Engine/Core-Concepts/02-MonoBehaviour-Lifecycle|MonoBehaviour Lifecycle]]