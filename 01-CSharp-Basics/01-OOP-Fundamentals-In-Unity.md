---
tags:
  - csharp/oop
  - unity/architecture
date_created: 2026-09-22
aliases:
  - Object Oriented Programming
  - Interfaces vs Abstract Classes
---

# 🧬 Object-Oriented Programming & Composition in Unity

Unity uses a hybrid approach combining traditional Object-Oriented Programming (OOP) with Component-Based Architecture (`Entity-Component`).

---

## 1. Interfaces vs. Abstract Classes

| Feature | Interface (`IInteractable`) | Abstract Class (`BaseEnemy`) |
| :--- | :--- | :--- |
| **Multiple Inheritance** | Yes (Implement multiple interfaces) | No (Single class inheritance limit) |
| **Field State** | Cannot contain instance state/fields | Holds member variables and state |
| **Use Case** | Cross-cutting traits (`IDamageable`, `IInteractable`) | Hierarchical base types with shared logic |

### Interface Pattern for Decoupled Systems

```csharp
public interface IDamageable
{
    void TakeDamage(float amount);
}

public class EnemyHealth : MonoBehaviour, IDamageable
{
    [SerializeField] private float health = 100f;

    public void TakeDamage(float amount)
    {
        health -= amount;
        if (health <= 0) Destroy(gameObject);
    }
}
````

## 2. Composition Over Inheritance

Prefer composing game entities out of specialized, modular components rather than deep, rigid inheritance trees.

- **Inheritance Bottleneck:** `Player -> Character -> Entity -> MonoBehaviour` (Hard to refactor).
    
- **Composition Approach:** `Player` entity attaches `HealthComponent`, `MovementComponent`, and `InputReceiver`.
    

## 🔗 Related Vault Notes

- [[01-CSharp-Basics/02-Delegates-Events-And-Actions|Delegates and Events]]
    
- [[03-Game-Architecture/02-State-Machine-Pattern|State Machine Pattern]]