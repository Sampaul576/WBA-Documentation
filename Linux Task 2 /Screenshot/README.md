# Linux Task 02: Users, Groups & File Permissions

**Name:** Rithik Raj 


---

## Objective

Understand Linux user management, groups, file ownership, and file permissions — the foundation of Linux security and system administration.

---

## Part A: Understanding Users

### Commands Run

```bash
whoami
id
cat /etc/passwd
```

| Question | Answer |
|----------|--------|
| Current Username | [lostlog] |
| What is UID? | UID (User ID) is a unique number the Linux system assigns to each user. Root always has UID 0. It identifies who owns a process or file. |
| What is GID? | GID (Group ID) is the primary group number assigned to a user. It determines which group's permissions apply by default. |
| What does /etc/passwd contain? | It stores one entry per user containing: username, password placeholder (x), UID, GID, home directory, and default shell. |

---

## Part B: Create Users & Groups

### Commands Used

```bash
# Create groups
sudo groupadd interns
sudo groupadd cyberteam

# Create users
sudo useradd student1
sudo useradd student2
sudo useradd student3

# Add users to groups
sudo usermod -aG interns student1
sudo usermod -aG interns student2
sudo usermod -aG cyberteam student3

# Verify
groups
id student1
id student2
```

## Part C: File Ownership

### Commands Used

```bash
# Create project folder and files
mkdir ~/CyberSecurity_Project
cd ~/CyberSecurity_Project
touch report.txt notes.txt credentials.txt

# Check ownership before change
ls -l

# Change ownership of report.txt to student1
sudo chown student1 report.txt

# Check ownership after change
ls -l
```

### Ownership Summary

| File | Original Owner | New Owner | Command Used |
|------|---------------|-----------|--------------|
| report.txt | [lostlog] | student1 | `sudo chown student1 report.txt` |
| notes.txt | [lostlog] | (unchanged) | — |
| credentials.txt | [lostlog] | (unchanged) | — |

## Part D: File Permissions

### Commands Used

```bash
touch ~/security_policy.txt
cd ~

# Stage 1 — Read Only
chmod 444 security_policy.txt
ls -l security_policy.txt

# Stage 2 — Read & Write
chmod 664 security_policy.txt
ls -l security_policy.txt

# Stage 3 — Full Access
chmod 777 security_policy.txt
ls -l security_policy.txt
```

### Permission Stages

| Stage | chmod Value | Symbolic | Screenshot |
|-------|-------------|----------|------------|
| Read Only | `444` | `r--r--r--` | *[screenshot]* |
| Read & Write | `664` | `rw-rw-r--` | *[screenshot]* |
| Full Access | `777` | `rwxrwxrwx` | *[screenshot]* |

---

## Part E: Permission Analysis

| Permission | Owner Rights | Group Rights | Other Rights | Real-World Use Case |
|------------|-------------|--------------|--------------|---------------------|
| `755` | rwx (read, write, execute) | r-x (read, execute) | r-x (read, execute) | Web server directories — owner manages files, everyone can browse |
| `644` | rw- (read, write) | r-- (read only) | r-- (read only) | Configuration files — only owner edits, others can read |
| `777` | rwx (full) | rwx (full) | rwx (full) | ⚠️ Avoid in production — everyone has full control, major security risk |
| `600` | rw- (read, write) | --- (none) | --- (none) | SSH private keys, password files — strictly private to owner |
| `700` | rwx (full) | --- (none) | --- (none) | Personal scripts or sensitive directories — owner-only access |

---

## Part F: Security Challenge

As a Linux Administrator, here are the recommended permissions for sensitive files:

| File | Recommended Permission | Reason |
|------|----------------------|--------|
| `password_backup.txt` | `600` | Extremely sensitive. Only the owner should be able to read or write it. No group or public access. |
| `public_notice.txt` | `644` | Intended for all users to read. Only the admin (owner) should be able to edit it. |
| `system_log.txt` | `640` | Admin and the sysadmin group need to read logs for monitoring. General users should not access log data. |
| `personal_notes.txt` | `600` | Private to the individual. No reason for anyone else to have access. |

---

## Part G: Linux Security Research

### 1. Why are file permissions important?

File permissions are the primary mechanism Linux uses to control who can read, modify, or run a file. Without proper permissions, any user or process on the system could access or destroy data belonging to others. They prevent unauthorized access, protect sensitive information, and reduce the impact of security breaches.

### 2. What happens if sensitive files are given 777 permissions?

With 777, every user on the system — including attackers who have gained a low-privilege account — can read, modify, or delete the file. A file like `/etc/shadow` (which stores hashed passwords) with 777 would expose all user password hashes to anyone, making the entire system easy to compromise.

### 3. What is the Principle of Least Privilege?

The Principle of Least Privilege means giving every user, program, or process only the minimum level of access they need to perform their specific task — nothing extra. For example, a web server only needs read access to serve files, not write access. This limits the damage an attacker can do if they compromise one account or service.

### 4. Why do organizations restrict user access?

Organizations restrict access to:
- Prevent accidental deletion or modification of critical files
- Limit damage if an employee account is hacked
- Meet compliance requirements (such as GDPR, HIPAA, or ISO 27001)
- Enforce accountability — knowing who can access what makes auditing easier
- Protect intellectual property and confidential data from insider threats

---

## Folder Structure

```
Linux_Task_02_YourName/
├── README.md
├── screenshots/
│   ├── partA_whoami.png
│   ├── partA_id.png
│   ├── partA_passwd.png
│   ├── partB_id_student1.png
│   ├── partB_id_student2.png
│   ├── partC_ls_before.png
│   ├── partC_ls_after.png
│   ├── partD_readonly.png
│   ├── partD_readwrite.png
│   └── partD_fullaccess.png

```

