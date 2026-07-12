# 🚩 Linux Privilege Escalation

> 📌 **Goal:** Understand Linux privilege escalation, why it happens, common weaknesses, enumeration techniques, and how security professionals identify and prevent privilege escalation vulnerabilities.

---

# 📚 Table of Contents

1. 🔐 [What is Privilege Escalation?](#-what-is-privilege-escalation)
2. 👑 [Linux Privilege Levels](#-linux-privilege-levels)
3. ⚠️ [Why Privilege Escalation Happens](#️-why-privilege-escalation-happens)
4. 🔄 [Types of Privilege Escalation](#-types-of-privilege-escalation)
5. 🕵️ [Linux Enumeration](#️-linux-enumeration)
6. 👤 [User Enumeration](#-user-enumeration)
7. 🔑 [Sudo Enumeration](#-sudo-enumeration)
8. ⚡ [SUID and SGID Permissions](#️-suid-and-sgid-permissions)
9. 📂 [File Permission Weaknesses](#-file-permission-weaknesses)
10. ⏰ [Cron Job Vulnerabilities](#️-cron-job-vulnerabilities)
11. 🧩 [PATH Variable Vulnerabilities](#-path-variable-vulnerabilities)
12. 🐧 [Kernel Vulnerabilities](#-kernel-vulnerabilities)
13. 🛠️ [Privilege Escalation Tools](#️-privilege-escalation-tools)
14. 🛡️ [Preventing Privilege Escalation](#️-preventing-privilege-escalation)


---

# 🔐 What is Privilege Escalation?

Privilege escalation is the process of gaining higher-level permissions than the permissions originally assigned to a user.

In Linux, users have different levels of access.

Example:

```
Normal User
     |
     |
     ↓
Root User
```

A normal user has limited access, while the root user has complete control over the operating system.

Privilege escalation happens when a user discovers a weakness that allows them to perform actions normally restricted to another user or administrator.


Example:

```
Low Privileged User
          |
          ↓
Higher Privileged User
          |
          ↓
Root Access
```


Privilege escalation is an important concept in cybersecurity because attackers often try to increase their permissions after gaining initial access to a system.

Ethical hackers study privilege escalation to find and fix these weaknesses before attackers exploit them.


---

# 👑 Linux Privilege Levels

Linux mainly has two types of users:

- 👤 Normal Users
- 👑 Root User


# 👤 Normal User

A normal user is an account with limited permissions.

Normal users usually:

- Cannot modify system files.
- Cannot manage all services.
- Cannot access protected files.
- Cannot create system-level changes.


Example:

```bash
whoami
```

Output:

```
student
```


Check user information:

```bash
id
```


Example:

```
uid=1000(student)
gid=1000(student)
```


---

# 👑 Root User

The root user is the administrator account in Linux.

Root has unlimited permissions.

Root UID:

```
0
```


Root can:

- Modify any file.
- Install software.
- Create and delete users.
- Change system configurations.
- Manage services.
- Access protected information.


Example:

```bash
whoami
```

Output:

```
root
```


The root account is powerful but dangerous because mistakes can damage the entire system.


---

# ⚠️ Why Privilege Escalation Happens

Privilege escalation occurs because of security weaknesses.

Common reasons include:


# 🔓 Misconfiguration

Incorrect system settings can create security problems.

Examples:

- Weak file permissions.
- Unsafe sudo rules.
- Incorrect service configuration.


Example:

A normal user having permission:

```
sudo ALL=(ALL) ALL
```

can execute commands as root.


---

# 🐞 Software Vulnerabilities

Programs may contain security bugs.

Examples:

- Outdated applications.
- Vulnerable services.
- Kernel vulnerabilities.


Attackers can abuse these weaknesses to gain higher privileges.


---

# 🔑 Weak Authentication

Poor authentication can allow unauthorized access.

Examples:

- Weak passwords.
- Reused passwords.
- Exposed credentials.


---

# 👥 Excessive Permissions

Users should only have the permissions they need.

Giving unnecessary permissions increases security risks.


Example:

A regular employee account should not have full administrator privileges.


---

# 🔄 Types of Privilege Escalation


# 🟢 Vertical Privilege Escalation

Vertical escalation means moving from a lower privilege level to a higher privilege level.


Example:

```
Normal User
      |
      ↓
Administrator
      |
      ↓
Root
```


This is the most common privilege escalation type in Linux.


---

# 🔵 Horizontal Privilege Escalation

Horizontal escalation means accessing another user's account with the same privilege level.


Example:

```
User A
  |
  ↓
User B
```


Example:

A user accessing another user's private files.


---

# 🕵️ Linux Enumeration

Enumeration is the process of collecting information about a system.

Before looking for vulnerabilities, security professionals gather information about:

- Users.
- Groups.
- Permissions.
- Services.
- Applications.
- Operating system details.


---

# 🖥️ System Information Gathering


## Check Hostname

```bash
hostname
```


Example output:

```
kali-machine
```


---

## Check Operating System

```bash
cat /etc/os-release
```


Example:

```
NAME="Kali GNU/Linux"
```


---

## Check Kernel Version

```bash
uname -a
```


Example:

```
Linux kali 6.x.x
```


Kernel information helps identify possible vulnerabilities.


---

# 👤 User Enumeration


## Current User

```bash
whoami
```


Example:

```
student
```


---

## User Information

```bash
id
```


Example:

```
uid=1000(student)
gid=1000(student)
groups=student,sudo
```


---

## View All Users

Linux stores users in:

```
/etc/passwd
```


View:

```bash
cat /etc/passwd
```


Example:

```
john:x:1001:1001:/home/john:/bin/bash
```


---

# 👥 Group Enumeration


View groups:

```bash
cat /etc/group
```


Check current groups:

```bash
groups
```


Groups determine what permissions users have.


---

# 🔑 Sudo Enumeration

Sudo allows users to execute commands with administrator privileges.


Check sudo permissions:

```bash
sudo -l
```


Example:

```
User student may run:
(root) /usr/bin/python3
```


This information shows what commands can run with elevated privileges.


---

# ⚡ SUID and SGID Permissions

Linux has special permissions:

- SUID
- SGID
- Sticky Bit


These permissions modify normal execution behavior.


---

# 🔴 SUID (Set User ID)

SUID allows a program to run using the owner's permissions.


Normal:

```
User runs program
        |
        ↓
Uses user's permissions
```


With SUID:

```
User runs program
        |
        ↓
Uses owner's permissions
```


Example:

```
Root owns program
        |
        ↓
User executes program
        |
        ↓
Program runs as root
```


SUID numeric value:

```
4000
```


Example:

```bash
chmod 4755 program
```


Find SUID files:

```bash
find / -perm -4000 2>/dev/null
```


---

# 🔵 SGID (Set Group ID)

SGID works similar to SUID but applies to groups.


Numeric value:

```
2000
```


Example:

```bash
chmod 2775 directory
```


SGID allows files created inside a directory to inherit the directory group.


---

# 🟢 Sticky Bit

Sticky Bit is mainly used on shared directories.


It allows users to create files but only delete their own files.


Example:

```
/tmp
```


Check:

```bash
ls -ld /tmp
```


Output:

```
drwxrwxrwt
```


The last:

```
t
```

represents Sticky Bit.


Numeric value:

```
1000
```


Example:

```bash
chmod 1777 folder
```


---

# 📂 File Permission Weaknesses

Linux permissions control:

- Owner
- Group
- Others


Check:

```bash
ls -l
```


Example:

```
-rwxrwxrwx file.txt
```


This is dangerous because everyone can modify the file.


---

# 🔍 Finding Writable Files

```bash
find / -writable 2>/dev/null
```


Writable files can become security risks if important programs depend on them.


---

# ⏰ Cron Job Vulnerabilities

Cron is a Linux scheduling service.

It runs commands automatically at specific times.


View user cron jobs:

```bash
crontab -l
```


System cron locations:

```bash
ls /etc/cron*
```


Example:

```
Root runs backup script
```

If a normal user can modify that script:

```
User modifies script
        |
        ↓
Root executes script
```


This creates a privilege escalation risk.


---

# 🧩 PATH Variable Vulnerabilities

PATH tells Linux where to search for commands.


View PATH:

```bash
echo $PATH
```


Example:

```
/usr/bin:/bin
```


A dangerous PATH configuration may allow unauthorized programs to execute.


Check:

```bash
echo $PATH
```


Security practice:

Never add untrusted directories to PATH.


---

# 🐧 Kernel Vulnerabilities

The Linux kernel controls communication between hardware and software.


Old kernels may contain vulnerabilities.


Check kernel:

```bash
uname -r
```


Security risks:

- Outdated kernel.
- Missing security patches.
- Known vulnerabilities.


Protection:

```bash
sudo apt update
sudo apt upgrade
```


---

# 🛠️ Privilege Escalation Tools

Security professionals use enumeration tools to identify weaknesses.


Common tools:

## LinPEAS

A Linux enumeration script.

Used to find:

- SUID files.
- Weak permissions.
- Credentials.
- Misconfigurations.


## Linux Exploit Suggester

Checks kernel vulnerabilities.


## LES (Linux Exploit Suggester)

Searches for possible kernel exploits.


These tools should only be used on systems you have permission to test.


---

# 🛡️ Preventing Privilege Escalation


## 🔒 Follow Least Privilege Principle

Users should only have required permissions.


---

## 🔄 Update Systems

Keep software updated:

```bash
sudo apt update
sudo apt upgrade
```


---

## 🔐 Secure sudo Configuration

Edit:

```bash
sudo visudo
```


Avoid unnecessary permissions.


---

## ⚡ Monitor SUID Files

Regularly check:

```bash
find / -perm -4000 2>/dev/null
```


---

## 📂 Secure File Permissions

Avoid:

```
777
```

permissions on important files.


---

## 📝 Monitor Logs

Important logs:

```
/var/log/auth.log
```


Monitor:

- Failed login attempts.
- User creation.
- Privilege changes.


---

