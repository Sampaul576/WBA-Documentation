# Linux Task 03 — Process Management, System Monitoring & Shell Scripting

**Name:** V Sam Paul
**Date:** 14-06-2025
**Internship Task:** Task 03

---

## Overview

This task covers Linux process management, system monitoring commands, shell scripting, service status checks, and security monitoring tools. These are core skills used by Linux Administrators, SOC Analysts, and Cyber Security Professionals.

---

## Folder Structure

```
Linux_Task_03_YourName/
├── screenshots/
│   ├── partA_ps.png
│   ├── partA_ps_aux.png
│   ├── partA_top.png
│   ├── partA_htop.png
│   ├── partB_sleep_process.png
│   ├── partB_kill.png
│   ├── partC_free.png
│   ├── partC_df.png
│   ├── partC_uptime.png
│   ├── partC_uname.png
│   ├── partD_ssh_status.png
│   ├── partD_network_status.png
│   ├── partE_script_output.png
│   └── partF_security_commands.png
└── README.md
```

---

## Part A — Process Monitoring

### Commands Run
```bash
ps
ps aux
top
htop
```

### Questions & Answers

**What is a Process?**
A process is a running instance of a program. Every command, application, or service running on a Linux system is a process managed by the OS kernel.

**What is a PID?**
A PID (Process ID) is a unique number assigned by the operating system to every running process. It is used to identify and manage processes.


## Part B — Process Management

### Commands Run
```bash
# Terminal 1
sleep 300

# Terminal 2
ps aux | grep sleep
kill <PID>
kill -9 <PID>
```

### Documentation

| Field | Details |
|---|---|
| PID Found | *(your PID here)* |
| Command Used | `kill <PID>` / `kill -9 <PID>` |
| Result | Process terminated — Terminal 1 displayed "Terminated" |

**Difference between `kill` and `kill -9`:**
- `kill <PID>` sends SIGTERM (signal 15) — asks the process to terminate gracefully.
- `kill -9 <PID>` sends SIGKILL (signal 9) — forces immediate termination with no cleanup.

---

## Part C — System Monitoring

### Commands Run
```bash
free -h
df -h
uptime
uname -a
```

### System Summary Report

| Metric | Value |
|---|---|
| Total RAM | *(e.g., 4.0 GB)* |
| Available RAM | *(e.g., 2.1 GB)* |
| Disk Usage | *(e.g., 18G used / 50G total)* |
| System Uptime | *(e.g., 2 hours, 14 minutes)* |
| Kernel Version | *(e.g., Linux kali 6.1.0-kali9-amd64)* |

---

## Part D — Service Monitoring

### Commands Run
```bash
systemctl status ssh
systemctl status NetworkManager
```

### Questions & Answers

**What is a Service?**
A service is a background process (daemon) that runs continuously and performs system functions — such as handling SSH connections, managing network interfaces, or scheduling tasks.

**Why are services important?**
Services power the core functionality of a system. Without them, critical features like remote access, networking, logging, and scheduling would be unavailable.

**How can a stopped service affect a system?**
A stopped service disables the functionality it provides. For example:
- SSH stopped → no remote login access
- NetworkManager stopped → loss of network connectivity
- Cron stopped → scheduled tasks won't run

This can cause serious disruptions in both production systems and security operations.

---

## Part E — Shell Script

### Script: `system_report.sh`

```bash
#!/bin/bash
echo "================================"
echo "   System Information Report"
echo "================================"
echo "User:              $(whoami)"
echo "Hostname:          $(hostname)"
echo "Date & Time:       $(date '+%d-%m-%Y %H:%M:%S')"
echo "Current Directory: $(pwd)"
echo ""
echo "--- Memory Usage ---"
free -h
echo ""
echo "--- Disk Usage ---"
df -h
echo "================================"
```

### How to Run
```bash
chmod +x system_report.sh
bash system_report.sh
```

---

## Part F — Security Monitoring Commands

### Commands Run
```bash
netstat -tuln
ss -tuln
who
w
last
```

### Research Summary

| Command | Purpose | Example Use | Security Use Case |
|---|---|---|---|
| `netstat` | Displays active network connections, routing tables, and listening ports | `netstat -tuln` | Identify unauthorized open ports or unexpected outbound connections |
| `ss` | Modern, faster replacement for netstat — shows socket statistics | `ss -tuln` | Same as netstat; preferred on modern systems |
| `who` | Shows which users are currently logged in and from where | `who` | Detect unexpected or unauthorized active sessions |
| `w` | Shows logged-in users and what commands they are currently running | `w` | Identify suspicious user activity in real time |
| `last` | Displays login history — who logged in, when, and from where | `last` | Audit past access; spot repeated failed logins or unusual login times |

---

## Part G — Mini SOC Activity

*Scenario: A system is running slowly. You are a Security Analyst investigating.*

### 1. How would you identify resource-heavy processes?

I would start with `top` or `htop` to get a live view of all running processes sorted by CPU and memory usage. The highest consumers appear at the top. I would look for processes with unusually high resource usage compared to what they normally consume, and note their PID, name, and the user running them.

### 2. How would you determine whether a process is suspicious?

I would check:
- **Process name** — does it match a known application?
- **User running it** — is a system process running under an unexpected user account?
- **Start time** — was it launched at an unusual hour?
- **Network activity** — using `ss -p` or `netstat`, does it have unexpected open connections?
- **Parent process (PPID)** — what launched it? A suspicious child process with an unexpected parent is a red flag.

A process with a random or disguised name, running as root, making outbound connections to unknown IPs would be treated as suspicious.

### 3. What information would you collect before terminating a process?

Before terminating any process, I would collect:
- Full process name and PID (`ps aux | grep <name>`)
- The user account running it
- PPID (parent process) to understand what spawned it
- Open network connections (`ss -p`)
- Files it may be accessing or writing to
- Start time and how long it has been running

Only after documenting all of this would I use `kill <PID>` (graceful) or `kill -9 <PID>` (forced). This documentation is important for incident reporting and to avoid accidentally terminating a critical system process.

---

## Key Learnings

- Every running program is a process with a unique PID assigned by the kernel
- `kill` sends a graceful termination signal; `kill -9` forces immediate termination
- Services are long-running background processes essential to system function
- Shell scripts allow repetitive monitoring tasks to be automated
- Security analysts use `ss`, `who`, `w`, and `last` as first-response tools to detect anomalies

---
