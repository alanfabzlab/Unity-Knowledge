---
tags:
  - unity/architecture
  - design-patterns
  - state-machine
date_created: 2026-09-22
aliases:
  - Finite State Machine
  - FSM Pattern
---

# 🔄 Finite State Machine (FSM) Pattern

Finite State Machines (FSMs) organize complex gameplay states (e.g., Player `Idle`, `Running`, `Jumping`, `Attacking`) into decoupled state classes, preventing bloated conditional logic.

---

## 1. Pure C# State Machine Implementation

```csharp
public interface IState
{
    void Enter();
    void Update();
    void Exit();
}

public class StateMachine
{
    public IState CurrentState { get; private set; }

    public void Initialize(IState startingState)
    {
        CurrentState = startingState;
        CurrentState.Enter();
    }

    public void ChangeState(IState newState)
    {
        CurrentState?.Exit();
        CurrentState = newState;
        CurrentState.Enter();
    }

    public void Update()
    {
        CurrentState?.Update();
    }
}
````

## 2. Concrete State Example


```csharp
public class PlayerIdleState : IState
{
    private readonly PlayerController _player;
    private readonly StateMachine _stateMachine;

    public PlayerIdleState(PlayerController player, StateMachine stateMachine)
    {
        _player = player;
        _stateMachine = stateMachine;
    }

    public void Enter() => Debug.Log("Entered Idle State");
    public void Update()
    {
        if (_player.MoveInput != UnityEngine.Vector2.zero)
        {
            _stateMachine.ChangeState(_player.MoveState);
        }
    }
    public void Exit() => Debug.Log("Exited Idle State");
}
```

## 🔗 Related Vault Notes

- [[01-CSharp-Basics/01-OOP-Fundamentals-In-Unity|OOP Fundamentals]]
    
- [[03-Game-Architecture/01-ScriptableObject-Architecture|ScriptableObject Architecture]]