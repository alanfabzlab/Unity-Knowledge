---
tags:
  - unity/input
  - unity/packages
date_created: 2026-09-22
aliases:
  - New Input System
  - Action Maps
---

# 🎮 Unity Input System Package Architecture

The modern Unity Input System (`com.unity.inputsystem`) decouples physical input hardware (gamepads, keyboards, touch) from game logic via **Action Maps**.

---

## 1. Key Concepts

* **InputActionAsset:** Central asset file storing Control Schemes and Action Maps (e.g., `Player`, `UI`).
* **Action Types:**
  * **Value:** Continuous inputs like Vector2 sticks or triggers.
  * **Button:** Binary press/release events.
  * **Pass-Through:** Processes all incoming device inputs without arbitration.

---


## 2. Event-Driven Input Integration (C# Class Generation)

```csharp
using UnityEngine;
using UnityEngine.InputSystem;

public class PlayerInputHandler : MonoBehaviour, PlayerInputActions.IPlayerActions
{
    private PlayerInputActions _inputActions;

    private void Awake()
    {
        _inputActions = new PlayerInputActions();
        _inputActions.Player.SetCallbacks(this);
    }

    private void OnEnable() => _inputActions.Player.Enable();
    private void OnDisable() => _inputActions.Player.Disable();

    public void OnMove(InputAction.CallbackContext context)
    {
        Vector2 moveVector = context.ReadValue<Vector2>();
        // Pass vector to movement controller
    }

    public void OnJump(InputAction.CallbackContext context)
    {
        if (context.started)
        {
            // Execute jump logic
        }
    }
}
````

## 🔗 Related Vault Notes

- [[01-CSharp-Basics/02-Delegates-Events-And-Actions|Delegates and Events]]
    
- [[02-Unity-Engine/Core-Concepts/01-Unity-Ecosystem-Overview|Ecosystem Overview]]