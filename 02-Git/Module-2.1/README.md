## Module 2.1: Git Fundamentals & Version Control

When building complex drone software, collaborating with other engineers, or fine-tuning delicate autopilot code, keeping track of changes is critical to avoiding permanent software failures.

---

### Core Concepts

#### What is Git?
Git is a fast, distributed version control system that tracks changes made to files over time. It takes snapshots of your project folder at specific moments, allowing you to view its history, compare modifications, or jump back to an older version whenever you need to.

#### What is Version Control?
Version control is the practice of tracking and managing changes to software code. Instead of manually creating endless duplicate files, a version control system acts as a ledger that logs exactly **who** changed **what** line of code, **when**, and **why**.

#### What problem does Git solve?
Before Git, collaboration and tracking changes looked like this: `main_script.py`, `main_script_final.py`, `main_script_final_v2_TESTED.py`. 
* Git eliminates this chaotic mess.
* It prevents teammates from accidentally overwriting each other's code.
* It allows multiple people to work on the exact same project codebase simultaneously without breaking the master version.

#### What is a Repository?
A repository (or "repo") is the digital project folder where Git tracks everything. It contains all your project files, assets, documentation, and a hidden `.git` folder that keeps a meticulous record of every change, branch, and commit history.

---

### Git vs. GitHub

It is easy to confuse the two, but they serve completely different purposes:

| Feature | Git | GitHub |
|:---|:---|:---|
| **What is it?** | A localized software tool. | A cloud-based web platform. |
| **Location** | Runs locally on your machine (offline). | Hosted on remote cloud servers (online). |
| **Core Function** | Tracks code history and version control. | Hosts Git repositories online for sharing and collaboration. |
| **Interface** | Primarily used via the Terminal / CLI. | Visual web interface with project tools, issue tracking, and pull requests. |

---

### 💡 My Analogy for Git: The Video Game Save System

Think of Git like a **hardcore open-world video game with manual save slots and an interactive timeline**. 

* **The Codebase** is your current character state and progress in the game world.
* **A Commit** is you hitting "Save Game" before a major boss fight. You label the save: *"Saved before fighting the fire dragon."*
* **Branches** are like exploring parallel timelines. If you aren't sure whether to side with the Elves or the Orcs, you split the game. You try the Elves timeline on one save slot. If it ends up destroying your character layout, you don't lose anything—you just delete that timeline and go back to your safe master save slot.
* **GitHub** is like uploading your game saves to the cloud so your friend can download them, look at your progress, or jump in to play co-op on the exact same world state.

---

### Engineering Notes: Why Git is Vital in UAV Engineering

In robotics and drone development, Git is not just optional—it is a safety net:
* **Flight Parameter Backups:** Modifying mixer matrices or PID loops for a multirotor is risky. Committing working parameters ensures that if a new tuning attempt causes structural oscillations or a crash, you can instantly rollback the autopilot configuration to the last stable flight state.
* **Firmware Tracking:** Frameworks like PX4 and ArduPilot release frequent updates. Git allows you to maintain your own tailored custom firmware branch while easily pulling in upstream safety patches and updates from the global open-source community.
* **Multi-Disciplinary Collaboration:** On a drone team, software engineers write the navigation algorithms, control engineers adjust the flight dynamics, and hardware engineers export sensor configurations. Git integrates all of these moving parts into a unified, conflict-free build repository.

---

### Module 2.1 Summary
Today I learned the fundamental principles of version control and distinguished the local tracking capabilities of Git from the cloud hosting platform GitHub. Building a clear mental model of repositories and commit tracking showed me how to avoid messy code duplication. Applying this to UAV development highlighted how version control acts as an essential engineering safety net, ensuring that risky flight code variations or sensor configurations can be safely developed in parallel timelines without corrupting proven, flight-ready software configurations.
