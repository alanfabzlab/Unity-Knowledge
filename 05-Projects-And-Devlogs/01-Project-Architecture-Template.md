---
tags:
  - project/devlog
  - architecture/template
date_created: 2026-09-22
aliases:
  - Project Architecture Log
---

# 🎮 Project Name: Architecture & Devlog

Technical design specification and architectural devlog for active indie game projects.

---

## 1. Overview & Mechanics
* **Genre:** 2D Top-Down RPG
* **Engine / Version:** Unity 6 LTS
* **Render Pipeline:** Universal Render Pipeline (URP 2D)
* **Target Platforms:** PC / Steam Deck

---

## 2. Subsystem Breakdown

```text
GameManager (Persistent Singleton)
 ├── Input System (Action Maps: Gameplay, UI)
 ├── Player Entity (FSM: Idle, Run, Attack)
 └── Save System (JSON Local Storage / Cloud Save)
````

## 3. Technical Roadmap & Milestone Tracker

- [x] Core movement system & Input System mapping
    
- [x] Object Pool for projectiles
    
- [ ] ScriptableObject item & inventory database
    
- [ ] Save/Load pipeline implementation
    

## 🔗 Related Vault Notes

- [[03-Game-Architecture/01-ScriptableObject-Architecture|ScriptableObject Architecture]]
    
- [[03-Game-Architecture/02-State-Machine-Pattern|State Machine Pattern]]