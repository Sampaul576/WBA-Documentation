# 🐧 Linux Task 01 — Linux Environment Setup & Essential Commands

**Internship Task | Submitted by:** Rithik Raj
**VM Used:**  Kali 
---

## 📁 Folder Structure

```
Linux_Task_01_YourName/
│
├── README.md                   ← This file
├── Part_A_Installation/
│   ├── screenshot_desktop.png
│   ├── screenshot_terminal.png
│   └── screenshot_sysinfo.png
│
├── Part_B_Navigation/
│   ├── commands_output.txt
│   └── screenshots/
│
├── Part_C_Directory_Management/
│
├── Part_D_File_Management/
│ 
├── Part_E_System_Info/
└── Part_F_Research/
```

---

## ✅ Part A — Linux Installation & Verification

> Installed **[Ubuntu / Kali / Parrot]** on VirtualBox / VMware.

**Screenshots taken:**
- Desktop Environment → `Part_A_Installation/screenshot_desktop.png`
- Terminal Window → `Part_A_Installation/screenshot_terminal.png`
- System Information → `Part_A_Installation/screenshot_sysinfo.png`

---

## ✅ Part B — Basic Navigation Commands

> All commands run inside the Linux terminal on the VM.

| Command | Purpose | Screenshot |
|---------|---------|------------|
| `pwd` | Prints the current working directory (where you are in the file system) | ✅ |
| `ls` | Lists files and folders in the current directory | ✅ |
| `ls -la` | Lists all files including hidden ones, with permissions and sizes | ✅ |
| `cd` | Changes directory (navigate into folders) | ✅ |
| `clear` | Clears the terminal screen | ✅ |
| `history` | Shows list of previously run commands | ✅ |
| `whoami` | Displays the currently logged-in username | ✅ |
| `hostname` | Displays the name of the machine/system | ✅ |

**Command outputs saved to:** `Part_B_Navigation/commands_output.txt`

---

## ✅ Part C — Directory Management

### Folder Structure Created:

```
CyberSecurity_Lab/
├── Networking/
├── Linux/
├── CyberSecurity/
├── EthicalHacking/
└── Reports/
```

### Commands Used:

```bash
mkdir -p CyberSecurity_Lab/{Networking,Linux,CyberSecurity,EthicalHacking,Reports}
cd CyberSecurity_Lab
tree
```

| Command | Purpose |
|---------|---------|
| `mkdir` | Creates a new directory |
| `mkdir -p` | Creates nested directories in one command |
| `cd` | Navigate into a folder |
| `tree` | Visually displays the folder structure |

**Screenshots saved to:** `Part_C_Directory_Management/screenshots/`

---

## ✅ Part D — File Management

### Files Created Inside Folders:

```bash
touch notes.txt commands.txt report.txt
```

### All Operations Performed:

| Operation | Command Used | Purpose |
|-----------|-------------|---------|
| Create file | `touch notes.txt` | Creates a new empty file |
| Copy file | `cp notes.txt Linux/` | Copies file to another folder |
| Move file | `mv report.txt Reports/` | Moves file to another folder |
| Rename file | `mv notes.txt mynotes.txt` | Renames a file |
| Delete file | `rm commands.txt` | Permanently deletes a file |

**Command log saved to:** `Part_D_File_Management/commands_used.txt`

---

## ✅ Part E — System Information Collection

> Commands run to collect system details.

```bash
uname -a
hostname
whoami
date
uptime
pwd
```

### Output Summary:

| Info | Value |
|------|-------|
| Kernel Version | *(paste your output here)* |
| Username | *(paste your output here)* |
| Current Directory | *(paste your output here)* |
| Current Date & Time | *(paste your output here)* |
| System Uptime | *(paste your output here)* |

**Full output saved to:** `Part_E_System_Info/system_info_output.txt`

---

## ✅ Part F — Research Activity

> Written answers in own words. Full answers in `Part_F_Research/research_answers.md`

### 1. What is Linux?
Linux is a free and open-source operating system kernel created by Linus Torvalds in 1991. It powers a huge range of devices — from personal computers and servers to smartphones and supercomputers. Unlike Windows, the source code is publicly available and can be modified by anyone.

### 2. Why is Linux important in Cyber Security?
Linux gives security professionals full control over the system. Most cybersecurity tools (like Nmap, Metasploit, Wireshark, Burp Suite) run natively on Linux. It's also lightweight, stable, and lets professionals work directly with the command line — which is essential for security tasks.

### 3. Difference Between Linux and Windows

| Feature | Linux | Windows |
|---------|-------|---------|
| Cost | Free & open-source | Paid & proprietary |
| Security | More secure, less targeted | More targeted by malware |
| Customization | Highly customizable | Limited customization |
| CLI Usage | CLI-first environment | GUI-first environment |
| Usage in Servers | Dominates server market | Less common in servers |

### 4. What is a Linux Distribution?
A Linux Distribution (or "distro") is a version of Linux packaged with different software, tools, and a desktop environment. Examples include Ubuntu (beginner-friendly), Kali Linux (security-focused), Parrot OS (pentesting), and Arch Linux (advanced users).

### 5. Why Do Ethical Hackers Prefer Linux?
Ethical hackers prefer Linux because it comes pre-installed with hundreds of security and hacking tools (especially Kali Linux). It allows deep system-level access, runs efficiently even on older hardware, supports scripting and automation, and mirrors real-world server environments they test against.

---
