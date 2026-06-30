
## Module 1.2: Linux File System

### What is a file system?
It is the system's digital filing cabinet. It organizes and manages how data is stored and retrieved on a drive, keeping it structured in files and folders instead of a chaotic mess of data.

### What is the root directory?
Represented by a single forward slash (`/`), the root directory is the absolute base of the entire Linux system. Everything—files, programs, and drives—stems from this single starting point.

### Difference between absolute and relative paths.
* **Absolute Path:** The full address starting from the root (e.g., `/home/user/docs`). It works no matter where you are currently working.
* **Relative Path:** A shortcut address based on your current location (e.g., `docs/file.txt` or `../photos`).

---

### Important Linux directories

| Directory | Purpose |
|-----------|---------|
| `/` | **Root:** The starting point of the entire system. |
| `/home` | **User Home:** Personal files, documents, and settings. |
| `/etc` | **Configuration:** System settings and configuration files. |
| `/usr` | **User Apps:** Programs, libraries, and shared data. |
| `/var` | **Variable Data:** Frequently changing files like system logs. |
| `/tmp` | **Temporary:** Files needed briefly, often deleted on reboot. |
| `/dev` | **Devices:** Hardware components represented as files. |
| `/proc` | **Processes:** Virtual data about running programs and the system. |

---

![Linux Directory Tree Structure](../Images/Module_1.2.png)

### Module 1.2 Summary
Today I learned that Linux organizes everything into a single, clean tree structure starting at the root (`/`) directory. I discovered that even hardware devices are treated as files inside this system. I mastered the difference between absolute paths (full addresses) and relative paths (directional shortcuts). Understanding specific folders like `/etc` for settings and `/var` for logs helped demystify how Linux stays organized under the hood. Ultimately, navigating the terminal feels much easier now that I know how the filesystem layout works.
