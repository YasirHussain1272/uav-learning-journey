
## Module 1.3: File & Directory Manipulation

In Linux, managing files and directories efficiently is crucial for configuring flight controllers, managing build scripts, and organizing log files.

---

### File Management Commands

#### 1. `mkdir` (Make Directory)
* **Purpose:** Creates a new, empty directory.
* **Example:** `mkdir ~/uav_project`
* **UAV Use Case:** I would use `mkdir` to create a dedicated workspace folder for a new ROS 2 or PX4 simulation package.

#### 2. `rmdir` (Remove Directory)
* **Purpose:** Deletes an empty directory.
* **Example:** `rmdir ~/old_logs`
* **UAV Use Case:** I would use `rmdir` to clean up empty, unused build or export folders to keep my workspace organized.

#### 3. `touch`
* **Purpose:** Creates a new, empty file or updates the timestamp of an existing file.
* **Example:** `touch flight_params.txt`
* **UAV Use Case:** I would use `touch` to quickly create an empty configuration or checklist file before editing it with parameters.

#### 4. `cp` (Copy)
* **Purpose:** Copies files or directories from one location to another.
* **Example:** `cp config.pvh config_backup.pvh`
* **UAV Use Case:** I would use `cp` to make a backup of a PX4 configuration file before changing parameters so I can easily revert if a flight test fails.

#### 5. `mv` (Move / Rename)
* **Purpose:** Moves files or directories to a different path, or renames them.
* **Example:** `mv mission.plan current_mission.plan`
* **UAV Use Case:** I would use `mv` to move compiled binary files to the deployment folder, or to rename a waypoint mission file.

#### 6. `rm` (Remove)
* **Purpose:** Deletes files or directories (use `-r` for directories).
* **Example:** `rm temp_log.csv`
* **UAV Use Case:** I would use `rm` to permanently delete corrupted flight logs or temporary cache files to free up disk space.

#### 7. `cat` (Concatenate)
* **Purpose:** Displays the full contents of a file directly in the terminal.
* **Example:** `cat telemetry_status.log`
* **UAV Use Case:** I would use `cat` to quickly read small configuration files or verify the status messages inside a drone script.

#### 8. `tree`
* **Purpose:** Displays a visual, depth-indented tree graph of directories and files.
* **Example:** `tree ~/catkin_ws`
* **UAV Use Case:** I would use `tree` to double-check the structural layout of a ROS workspace to ensure nodes, launch files, and package configurations are in the right folders.

---

![File Manipulation Commands Summary](../Images/Module_1.3.png)

---

### Module 1.3 Summary
Today I learned how to create, copy, move, and destroy files and directories directly from the terminal. Connecting these commands to practical UAV scenarios showed me how vital command-line confidence is for managing flight parameters, structuring ROS workspaces, and safeguarding configuration backups. Visualizing the workspace layout with the `tree` command made it clear how directories interlink, which will save time when troubleshooting missing path errors in drone scripts.
