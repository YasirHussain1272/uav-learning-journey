
# Module 1: Linux Fundamentals

## Module 1.1: Introduction & Architecture

### What is an Operating System?
An Operating System (OS) is the software that manages a computer's hardware resources (CPU, memory, storage) and acts as an intermediary between the hardware and the applications you run.

---

### Why do UAV engineers use Linux?
UAV engineers use Linux because it is open-source, highly stable, and lightweight, allowing for deep customization on resource-constrained drone hardware. Additionally, standard robotics frameworks like **ROS**, **PX4**, **ArduPilot**, and **Gazebo** are natively built and optimized for Linux.

---

### Linux Architecture
* **Users / Applications:** The top layer where tools, scripts, and drone software run.
* **Shell (CLI):** The interface that interprets user commands and sends them to the kernel.
* **Kernel:** The core of the OS that directly controls the hardware and manages system resources.
* **Hardware:** The physical components (CPU, RAM, sensors, flight controllers).

---

### Commands Learned Today
* `pwd` – **P**rint **W**orking **D**irectory (shows your current folder path).
* `ls` – **L**i**s**t (displays files and folders in your current directory).
* `whoami` – Displays the username of the current terminal session.
* `uname -a` – Prints detailed system and Linux kernel information.
* `hostnamectl` – Shows system architecture, OS version, and device name settings.

![Linux Architecture Diagram](../Images/Module_1.1.png)

---

### Module 1.1 Summary
Today I learned the foundational layout of an operating system and why Linux is the industry standard for UAV and robotics development. I explored the layered architecture of Linux, understanding how commands flow from the user terminal down to the physical hardware components. Finally, I gained hands-on experience using the command line to navigate the filesystem and query core system information, which is essential for future drone simulation and configuration tasks.

***
