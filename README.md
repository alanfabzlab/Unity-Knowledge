


<div align="center">

# 🎮 Unity & C# Game Engineering Knowledge Base

[![Unity](https://img.shields.io/badge/Unity-2022.3%20LTS%20%7C%206.0-black?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com/)
[![C#](https://img.shields.io/badge/C%23-11.0%20%7C%2012.0-blueviolet?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![Obsidian](https://img.shields.io/badge/Obsidian-Vault-purple?style=for-the-badge&logo=obsidian&logoColor=white)](https://obsidian.md/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?style=for-the-badge)](LICENSE)

*A structured personal vault and documentation repository focused on Unity game engine architecture, C# scripting, design patterns, performance optimization, and indie game devlogs.*

</div>


<img src="https://capsule-render.vercel.app/api?type=waving&color=7C5CFF&height=60&section=header" width="100%" alt="Slow Neon Wave" />


## 🛠 Repository Structure

This vault is organized systematically to serve as a fast-lookup documentation hub and architectural reference during active game development:

📁 **Unity-Knowledge/**  
├── 📁 **00-Meta/** — *Templates, asset attachments, and vault configurations*  
│   └── 📁 **Templates/**  
│       └── 📄 [`Note-Template.md`](00-Meta/Templates/Note-Template.md)  
├── 📁 **01-CSharp-Basics/** — *Core language fundamentals, memory management, and OOP*  
│   ├── 📄 [`01-OOP-Fundamentals-In-Unity.md`](01-CSharp-Basics/01-OOP-Fundamentals-In-Unity.md)  
│   ├── 📄 [`02-Delegates-Events-And-Actions.md`](01-CSharp-Basics/02-Delegates-Events-And-Actions.md)  
│   └── 📄 [`03-Memory-Management-and-GC.md`](01-CSharp-Basics/03-Memory-Management-and-GC.md)  
├── 📁 **02-Unity-Engine/** — *Unity Scripting API, physics, lifecycle, and UI systems*  
│   ├── 📁 **Components/**  
│   │   └── 📄 [`01-Physics-Rigidbody-And-Colliders.md`](02-Unity-Engine/Components/01-Physics-Rigidbody-And-Colliders.md)  
│   ├── 📁 **Core-Concepts/**  
│   │   ├── 📄 [`01-Unity-Ecosystem-Overview.md`](02-Unity-Engine/Core-Concepts/01-Unity-Ecosystem-Overview.md)  
│   │   ├── 📄 [`02-MonoBehaviour-Lifecycle.md`](02-Unity-Engine/Core-Concepts/02-MonoBehaviour-Lifecycle.md)  
│   │   └── 📄 [`03-Async-Awaitables-And-Coroutines.md`](02-Unity-Engine/Core-Concepts/03-Async-Awaitables-And-Coroutines.md)  
│   └── 📁 **UI-And-Input/**  
│       └── 📄 [`01-Input-System-Package.md`](02-Unity-Engine/UI-And-Input/01-Input-System-Package.md)  
├── 📁 **03-Game-Architecture/** — *Design patterns, ScriptableObjects, and State Machines*  
│   ├── 📄 [`01-ScriptableObject-Architecture.md`](03-Game-Architecture/01-ScriptableObject-Architecture.md)  
│   └── 📄 [`02-State-Machine-Pattern.md`](03-Game-Architecture/02-State-Machine-Pattern.md)  
├── 📁 **04-Snippets-And-Scripts/** — *Production-ready C# utility scripts and helper methods*  
│   ├── 📄 [`01-Singleton-Pattern.md`](04-Snippets-And-Scripts/01-Singleton-Pattern.md)  
│   └── 📄 [`02-Object-Pooling.md`](04-Snippets-And-Scripts/02-Object-Pooling.md)  
└── 📁 **05-Projects-And-Devlogs/** — *Architectural breakdowns and logs for active games*  
    └── 📄 [`01-Project-Architecture-Template.md`](05-Projects-And-Devlogs/01-Project-Architecture-Template.md)

<img src="https://capsule-render.vercel.app/api?type=waving&color=7C5CFF&height=60&section=header" width="100%" alt="Slow Neon Wave" />


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


    
<img src="https://capsule-render.vercel.app/api?type=waving&color=7C5CFF&height=60&section=header" width="100%" alt="Slow Neon Wave" />



## 🕹 Featured Projects & Devlogs

### 👾 Indie 2D RPG Engine (In Development)

- **Genre:** 2D Top-Down / Pixel Art RPG
    
- **Tech Stack:** Unity, C#, Universal Render Pipeline (URP), Tilemaps
    
- **Focus Areas:** Custom State-Machine-based Movement & Combat, ScriptableObject Data-Driven Item System.

    
<img src="https://capsule-render.vercel.app/api?type=waving&color=7C5CFF&height=60&section=header" width="100%" alt="Slow Neon Wave" />


## 💻 Technical Setup

To preview and navigate this vault locally with full visual enhancements and query support:

1. Clone or open this repository inside **Obsidian**.
    
2. Enable **Community Plugins** in settings.
    
3. Recommended extensions configured in this vault: **Dataview**, **Codeblock Customizer**, **Mermaid Tools**, **Omnisearch**.


<img src="https://capsule-render.vercel.app/api?type=waving&color=7C5CFF&height=60&section=header" width="100%" alt="Slow Neon Wave" />
    

## 📜 License

This project is open-source and available under the [Creative Commons Attribution 4.0 International License](https://www.google.com/search?q=LICENSE&utm_source=gemini).
