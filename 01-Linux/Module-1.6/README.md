# Module 1.6: Environment Variables & Command Paths

## What is an Environment Variable?
An environment variable is a dynamic, system-wide variable that stores information about the operating system's environment. It acts like a global shortcut or configuration setting that any running program or terminal session can access to understand user preferences, paths, or system states.

---

## What is PATH?
`PATH` is one of the most critical environment variables in Linux. It contains a colon-separated list of directories (`/usr/bin`, `/bin`, etc.) where the operating system searches for executable files whenever you type a command in the terminal.

---

## Why does Linux find commands automatically?
When you type a command like `ls` or `git`, Linux doesn’t search the entire computer. Instead, it instantly looks through the specific folders listed inside your `$PATH` variable. If the executable file is found in one of those folders, it runs automatically.

---

## What does `which` do?
The `which` command locates the exact file path of the executable program that runs when you type a command. It helps you see which version of a tool (like Python) your system is currently using.

---

## What does `echo` do?
The `echo` command is used to print text or the values of environment variables directly to the terminal screen. To print a variable's value, you must prefix its name with a `$` sign.

---

## What does `export` do?
The `export` command sets an environment variable so that it is passed on to all child processes and programs started from that terminal session. Without `export`, the variable is only accessible locally within that exact shell instance.

---

## Why did we use `LIBGL_ALWAYS_SOFTWARE`?
We use `export LIBGL_ALWAYS_SOFTWARE=1` to force the system to render 3D graphics using CPU-based software rendering instead of relying on a physical graphics card (GPU). This is a vital troubleshooting step when running heavy drone simulators (like Gazebo) inside virtual environments, WSL, or systems with incompatible GPU drivers to prevent crashes.

---

## A UAV Engineering Example Using Environment Variables
In drone development, environment variables are heavily used to configure simulation environments without changing code. For example, when launching a simulation in ROS/PX4, you use variables to tell the system which drone model and world map to load:


## What I Learned Today
Today I mastered how the Linux operating system handles system configuration and command routing through environment variables. I learned that the $PATH variable is the hidden backbone that allows the terminal to locate and execute tools seamlessly without needing their absolute file paths. I also discovered how to use utility commands like which to audit executable locations and export to modify system parameters dynamically. Finally, I connected these concepts to UAV engineering, realizing how crucial environment variables are for switching drone models in software-in-the-loop (SITL) flight simulations and fixing graphic rendering bugs with LIBGL_ALWAYS_SOFTWARE.
```bash
export PX4_SIM_MODEL=iris_vision
export PX4_SIM_WORLD=mcmillan_airfield
ros2 launch px4_sitl simulation.launch.py
