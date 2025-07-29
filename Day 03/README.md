# 🛡️ Cybersecurity Notes - Day 04

This document summarizes key learnings and commands from Day 04 of the Cybersecurity course, covering basic Linux operations, malware analysis, and setup for Windows exploitation tools.

---

## ⚙️ Setting Up Tools in Kali Linux

### Download Visual Studio Code
You can install VS Code in Kali by downloading it from [VSCode Official Site](https://code.visualstudio.com/) or using `apt` if the repository is added.

VS Code is a powerful source-code editor with support for debugging, syntax highlighting, Git integration, and extensions—ideal for coding in Python, Bash, and more.

### Cloning a GitHub Repository
```bash
git clone https://github.com/keralahacker/Villain.git
```
- If cloning fails, download the repository as a ZIP and extract it manually.
- Navigate into the extracted folder:
```bash
cd Villain
```

### Installing Dependencies
```bash
pip3 install -r requirements.txt --break-system-packages
```
- `--break-system-packages` overrides protections in Kali that prevent modifying core Python packages.
- If `crypt` or any other package throws an error, install it manually:
```bash
pip3 install crypt
```

### Running the Tool
```bash
python3 villain.py
```
Villain is a tool used to exploit Windows systems. It typically creates reverse shells and facilitates post-exploitation activities.

---

## 🦠 Malware Analysis

### Types of Malware Analysis
- **Static Analysis**: Review malicious code without executing it. This includes checking for suspicious strings, headers, or structure.
- **Dynamic Analysis**: Run and monitor malware behavior in a controlled environment like a sandbox or virtual machine.

> Note: Many malware samples (e.g., `.pdf`, `.exe`) are compressed archives—essentially ZIP packages containing malicious payloads.

---

## 🐧 Essential Linux Commands

| Command          | Description                                                    |
|------------------|----------------------------------------------------------------|
| `pwd`            | Displays the current directory path. Example: `/home/kali`     |
| `ls`             | Lists files in the current directory                           |
| `tree`           | Displays directory structure visually as a tree (optional)     |
| `cd`             | Navigates to the home directory (`/home/kali`) automatically   |
| `cd ..`          | Moves one level up in directory hierarchy                      |
| `mkdir <name>`   | Creates a new directory                                        |
| `rmdir <name>`   | Removes a directory (only if empty)                            |
| `touch <name>`   | Creates an empty file                                          |
| `ls -lh`         | Lists files with detailed info (permissions, size, timestamp)  |
| `man <cmd>`      | Opens the manual page for any command                          |

> 💡 When you launch a terminal, you're placed in a directory, ready to run commands. Most file navigation and operations in Linux are done through terminal commands.

---

## 🔐 File Permissions & Navigation

- In `ls -l` output:
  - `x` means execute permission.
  - `d` means it's a directory.
  - If no `d`, it's a regular file.

Linux file permissions are displayed as combinations like `-rwxr--r--`:
- First character: file type (`d` = directory, `-` = file)
- Next characters: user, group, and others' permissions.

To learn more about `chmod` (changing file permissions), refer to [this guide](https://www.nexcess.net/help/what-is-chmod/).

---

## 🧠 Additional Notes

- macOS uses a Bash-style terminal similar to Linux.
- Linux is **case-sensitive**: `script.sh` ≠ `Script.sh`
- Always keep Kali up-to-date:
```bash
sudo apt update && sudo apt upgrade
```

---

## 🧩 Clarified & Previously Unexplained Terms

- **"Offisicated codes"** – This term seems like a typo or mistranslation. If you meant "obfuscated code", it refers to code that’s deliberately made difficult to read or understand (often used in malware).
- **"Break-system-packages"** – A special flag to install Python packages that are normally restricted on Linux distros like Kali, where system integrity is critical.
- **`.pdf, .exe as zip files`** – These file types sometimes contain embedded compressed content or behave like archives in structure. Malware can hide payloads within them by leveraging that format.

---

## 🚧 Open Questions

- ❓ Still not sure if “offisicated” was meant to be “obfuscated”? Let me know and I can add a dedicated explanation.

---
