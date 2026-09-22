


````
<div align="center">

# 🎮 Unity & C# Game Engineering Knowledge Base

[![Unity](https://img.shields.io/badge/Unity-2022.3%20LTS%20%7C%206.0-black?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com/)
[![C#](https://img.shields.io/badge/C%23-11.0%20%7C%2012.0-blueviolet?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![Obsidian](https://img.shields.io/badge/Obsidian-Vault-purple?style=for-the-badge&logo=obsidian&logoColor=white)](https://obsidian.md/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

*A structured personal vault and documentation repository focused on Unity game engine architecture, C# scripting, design patterns, performance optimization, and indie game devlogs.*

[Vault Architecture](#-repository-structure) • [Core Focus](#-core-learning-pillars) • [Active Projects](#-featured-projects--devlogs) • [Getting Started](#-getting-started)

</div>

---

## 🛠 Repository Structure

This vault is organized systematically to serve as a fast-lookup documentation hub and architectural reference during active game development:

```text
Unity-Knowledge/
├── 00-Meta/                  # Templates, asset attachments, and vault configurations
├── 01-CSharp-Basics/         # Core language fundamentals, memory management, and OOP
├── 02-Unity-Engine/          # Unity Scripting API, physics, lifecycle, and UI systems
├── 03-Game-Architecture/     # Design patterns, ScriptableObjects, and State Machines
├── 04-Snippets-And-Scripts/  # Production-ready C# utility scripts and helper methods
└── 05-Projects-And-Devlogs/  # Architectural breakdowns and logs for active games
````

## 🚀 Core Learning Pillars

- **Object Pooling:** Minimizing Garbage Collection (GC) allocations for bullet hells and particle systems.
    
- **Structs vs. Classes:** Memory layout, stack vs. heap allocations, and cache locality.
    
- **Async & Async/Await vs. Coroutines:** Modern asynchronous programming models in Unity.
    
- **Delegates, Events & Actions:** Decoupling game systems via publish-subscribe patterns.
    

- **MonoBehaviour Lifecycle:** Execution order (`Awake`, `OnEnable`, `Start`, `FixedUpdate`, `Update`).
    
- **Physics & Collision:** `Rigidbody`, `Collider`, Raycasting optimization, and layer collision matrices.
    
- **UI Toolkit & Unity UI (UGUI):** Scalable interfaces, event triggers, and canvas performance batching.
    
- **Input System Package:** Rebindable controls, action maps, and multi-device support.
    

- **Finite State Machines (FSM):** Clean player controller state handling (Idle, Run, Jump, Attack).
    
- **ScriptableObject Architecture:** Data-driven design, inventory systems, and modular game events.
    
- **Observer & Command Patterns:** Decoupled combat systems and undo/redo mechanics.
    

## 🕹 Featured Projects & Devlogs

- **Genre:** 2D Top-Down / Pixel Art RPG
    
- **Tech Stack:** Unity, C#, Universal Render Pipeline (URP), Tilemaps
    
- **Focus Areas:**
    
    - Custom State-Machine-based Movement & Combat
        
    - ScriptableObject Data-Driven Item/Inventory System
        
    - Seamless Scene Loading & Save System Architecture
        

## 💻 Technical Setup

To preview and navigate this vault locally with full visual enhancements and query support:

1. Clone or open this repository inside **Obsidian**.
    
2. Enable **Community Plugins** in settings.
    
3. Recommended extensions configured in this vault:
    
    - **Dataview:** Automated note indexing and querying.
        
    - **Codeblock Customizer:** Advanced C# code block styling.
        
    - **Mermaid Tools:** State machine and logic sequence diagramming.
        
    - **Omnisearch:** Deep code and note search engine.