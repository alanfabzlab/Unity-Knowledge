


<div align="center">

# 🎮 Unity & C# Game Engineering Knowledge Base

[![Unity](https://img.shields.io/badge/Unity-2022.3%20LTS%20%7C%206.0-black?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com/)
[![C#](https://img.shields.io/badge/C%23-11.0%20%7C%2012.0-blueviolet?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![Obsidian](https://img.shields.io/badge/Obsidian-Vault-purple?style=for-the-badge&logo=obsidian&logoColor=white)](https://obsidian.md/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?style=for-the-badge)](LICENSE)

*A structured personal vault and documentation repository focused on Unity game engine architecture, C# scripting, design patterns, performance optimization, and indie game devlogs.*

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

### 1. C# & Memory Optimization

- **Object Pooling:** Minimizing Garbage Collection (GC) allocations for bullet hells and particle systems.
    
- **Structs vs. Classes:** Memory layout, stack vs. heap allocations, and cache locality.
    
- **Async & Async/Await vs. Coroutines:** Modern asynchronous programming models in Unity.
    
- **Delegates, Events & Actions:** Decoupling game systems via publish-subscribe patterns.
    

### 2. Unity Engine Internals & API

- **MonoBehaviour Lifecycle:** Execution order (`Awake`, `OnEnable`, `Start`, `FixedUpdate`, `Update`).
    
- **Physics & Collision:** `Rigidbody`, `Collider`, Raycasting optimization, and layer collision matrices.
    
- **UI Toolkit & Unity UI (UGUI):** Scalable interfaces, event triggers, and canvas performance batching.
    
- **Input System Package:** Rebindable controls, action maps, and multi-device support.
    

### 3. Game Architecture & Design Patterns

- **Finite State Machines (FSM):** Clean player controller state handling (Idle, Run, Jump, Attack).
    
- **ScriptableObject Architecture:** Data-driven design, inventory systems, and modular game events.
    

## 🕹 Featured Projects & Devlogs

### 👾 Indie 2D RPG Engine (In Development)

- **Genre:** 2D Top-Down / Pixel Art RPG
    
- **Tech Stack:** Unity, C#, Universal Render Pipeline (URP), Tilemaps
    
- **Focus Areas:** Custom State-Machine-based Movement & Combat, ScriptableObject Data-Driven Item System.
    

## 💻 Technical Setup

To preview and navigate this vault locally with full visual enhancements and query support:

1. Clone or open this repository inside **Obsidian**.
    
2. Enable **Community Plugins** in settings.
    
3. Recommended extensions configured in this vault: **Dataview**, **Codeblock Customizer**, **Mermaid Tools**, **Omnisearch**.
    

## 📜 License

This project is open-source and available under the [Creative Commons Attribution 4.0 International License](https://www.google.com/search?q=LICENSE&utm_source=gemini).