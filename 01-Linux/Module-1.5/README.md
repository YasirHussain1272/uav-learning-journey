## Module 1.5: Linux Process Management

Monitoring and controlling processes ensures that resource-intensive drone software stacks, flight controllers, and video telemetry pipelines run smoothly without locking up the onboard computer.

---

### Core Process Concepts

#### What is a process?
A process is an active, executing instance of a program loaded into the system's memory. Whenever you open a terminal, run a simulation, or launch a script, Linux creates a process to handle it.

#### Difference between a program and a process
* **Program:** A passive, static set of instructions stored on your storage drive (e.g., the compiled `px4` software file). It does nothing on its own.
* **Process:** An active, dynamic entity loaded into RAM that actively uses CPU resources, memory, and system devices to execute those instructions.

#### What is a PID?
A PID (Process ID) is a unique numerical identifier assigned by the Linux kernel to every running process. The system uses this number to track resource consumption, manage permissions, and target specific tasks when pausing or stopping them.

---

### Process Monitoring Commands

#### 1. `ps` (Process Status)
* **Purpose:** Displays a snapshot of the currently active processes running in your current terminal session. 
* **Key Flag:** Using `ps -ef` lists every single process running across the entire system, showing the UID, PID, Parent PID (PPID), and command path.
* **UAV Use Case:** I would use `ps -ef | grep ros` to verify whether background ROS 2 nodes are hidden or still running after shutting down a simulation workspace.

![Process Status Summary with ps and ps -ef](../Images/Module_1.5_a.png)

#### 2. `top` vs `htop`
* **`top`:** The default, text-based system monitor built into almost all Linux systems. It displays a real-time, frequently updated list of active processes sorted by CPU usage, but lacks color and mouse support.
* **`htop`:** An interactive, visually enhanced process viewer. It features color-coded bar graphs for CPU and RAM usage per core, supports mouse clicks, and allows you to easily search, filter, and sort tasks without typing flags.

![Real-time Process Monitoring with top](../Images/Module_1.5_b.png)

![Interactive System Resource Monitoring with htop](../Images/Module_1.5_c.png)

#### 3. `kill`
* **Purpose:** Sends a termination signal to a process using its PID, forcing it to close down.
* **Example:** `kill -9 1234` (Forces process 1234 to stop immediately).
* **UAV Use Case:** I would use `kill` to forcefully shut down a frozen Gazebo simulation process that is locking up CPU resources before trying to restart a flight simulation.

---

### Engineering Notes: Process Monitoring in UAV Projects

Onboard an autonomous drone (e.g., using a Raspberry Pi or NVIDIA Jetson companion computer), process management directly prevents mission critical failures:
* **Resource Bottlenecks:** Real-time software like object detection networks or visual-inertial odometry (VIO) nodes can spike CPU consumption. Using `htop` helps pinpoint if a vision node is starving a critical obstacle avoidance script of processing power.
* **Ghost Processes:** Sometimes, when a drone simulation script crashes or is terminated incorrectly, the underlying physics engine (`gzserver` or `gazebo`) continues running invisibly in the background. If you don't find its PID with `ps` and terminate it with `kill`, the next simulation run will fail due to conflicting port and hardware access.

---

### Module 1.5 Summary
Today I learned how the Linux operating system manages active tasks using processes and unique Process IDs (PIDs). I explored how to get a quick snapshot of running tasks using `ps` and compared the classic layout of `top` with the interactive, color-coded dashboard of `htop` for live resource tracking. Understanding how to selectively manage these tasks with the `kill` command is highly practical for drone development, ensuring that locked background tasks or runaway vision scripts can be cleanly terminated to maintain reliable companion computer stability.
