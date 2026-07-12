# 🐧 Day 4: Further on Linux

> 📌 **Goal:** Understand the Linux file system hierarchy, learn text editors, and manage Linux users, permissions, and root access.

# 📚 Table of Contents

1. 📂 [Linux File Hierarchy](#-linux-file-hierarchy)
2. ✍️ [Text Editors](#️-text-editors)
3. 👥 [Linux User Management](#-linux-user-management)
4. 🔑 [Linux Users and Privileges](#-linux-users-and-privileges)
5. ➕ [Creating Users](#-creating-users)
6. 📄 [/etc/passwd and /etc/shadow](#-etcpasswd-and-etcshadow)
7. 👑 [Root User Access](#-root-user-access)


# 📂 Linux File Hierarchy

Linux organizes files using a hierarchical structure.

Unlike Windows, where drives are represented using letters like:

```text
C:
D:
E:
```

Linux uses a single root directory:

```text
/
```

Everything in Linux starts from the root directory.


Example:

```text
/
├── bin
├── etc
├── home
├── root
├── usr
└── var
```


# 📁 Important Linux System Directories

## `/` — Root Directory

The root directory is the top-level directory in Linux.

Everything exists inside `/`.

Example:

```bash
cd /
```


## `/bin` — Essential Commands

Contains basic commands needed by all users.

Examples:

```text
ls
cp
mv
cat
bash
```

These commands are required for basic system operation.


## `/sbin` — System Administration Commands

Contains commands mainly used by administrators.

Examples:

```text
iptables
fdisk
shutdown
reboot
```

Usually requires root privileges.


## `/etc` — Configuration Files

Contains system-wide configuration files.

Examples:

```text
/etc/passwd
/etc/shadow
/etc/hosts
/etc/network
```

Security tools and services store their configurations here.


## `/home` — User Directories

Contains personal files of normal users.

Example:

```text
/home/natnael
/home/student
```

Each user has their own home directory.


## `/root` — Root User Home

The home directory of the root user.

Example:

```bash
cd /root
```


Important:

```text
/root ≠ /
```

`/` is the system root.

`/root` is the root user's personal directory.


## `/usr` — User Programs

Contains installed applications and libraries.

Examples:

```text
/usr/bin
/usr/lib
/usr/share
```


## `/var` — Variable Data

Stores data that changes frequently.

Examples:

```text
Logs
Database files
Web server data
```

Example:

```text
/var/log
```

Contains system logs.


## `/tmp` — Temporary Files

Stores temporary files.

Usually cleared automatically after reboot.


## `/dev` — Device Files

Contains files representing hardware devices.

Examples:

```text
/dev/sda
/dev/usb
/dev/null
```


## `/proc` — Process Information

Virtual filesystem containing information about running processes.

Example:

```bash
cat /proc/cpuinfo
```

Shows CPU information.


## `/boot` — Boot Files

Contains files required to start Linux.

Examples:

```text
Kernel
GRUB bootloader
Boot configuration
```


## `/lib` — System Libraries

Contains essential libraries required by programs.


## `/opt` — Optional Software

Used for installing additional software packages.


## `/mnt` — Temporary Mount Point

Used to manually mount external storage devices.

Example:

```bash
mount /dev/sdb1 /mnt
```


## `/media` — Removable Devices

Automatically mounted devices.

Examples:

```text
USB drives
CD/DVD
External storage
```


# ✍️ Text Editors

Text editors allow users to create and modify files in Linux.

Common Linux text editors:

- 🟢 Nano
- 🔵 Vim


# 🟢 Nano Editor

Nano is a simple and beginner-friendly command-line text editor.

Open a file:

```bash
nano file.txt
```


Example:

```bash
nano notes.txt
```


## Nano Shortcuts

| Shortcut | Action |
|---|---|
| CTRL + O | Save file |
| CTRL + X | Exit |
| CTRL + W | Search |
| CTRL + K | Cut line |
| CTRL + U | Paste line |
| CTRL + G | Help |


Advantages:

- Easy to learn.
- Good for beginners.
- Simple configuration editing.


# 🔵 Vim Editor

Vim is a powerful and advanced text editor available in Linux.

Open a file:

```bash
vim file.txt
```


Vim works using different modes.


## Vim Modes


### Normal Mode

Used for navigation and commands.


### Insert Mode

Used for writing text.

Enter:

```text
i
```


### Command Mode

Used for saving and exiting.

Enter:

```text
:
```


## Important Vim Commands

Save:

```vim
:w
```


Exit:

```vim
:q
```


Save and exit:

```vim
:wq
```


Exit without saving:

```vim
:q!
```


## Vim Advantages

- Extremely powerful.
- Available on almost every Linux system.
- Supports plugins.
- Used by advanced users.


# 👥 Linux User Management

A user is a person or account that interacts with a computer system.

Every Linux user has:

- 👤 Username
- 🔢 User ID (UID)
- 👥 Group membership
- 📂 Home directory
- 🔐 Permissions


To check your current username:

```bash
whoami
```


Example:

```bash
whoami
```

Output:

```text
natnael
```


# 👥 Linux Groups

A group is a collection of users who share permissions.

Every user belongs to at least one group.


Example:

```text
User:
John

Groups:
developers
sudo
```


Groups help administrators manage permissions easily.


# 🔑 Linux Users and Privileges

Linux users have different levels of power.

There are two main types of users:


# 👑 Root User

The root user is the administrator of Linux.

Root UID:

```text
0
```


Root can:

- Install software.
- Delete system files.
- Change configurations.
- Manage users.
- Control the entire system.


Example:

```bash
rm -rf /
```

A root user can execute dangerous commands like this.


# 👤 Normal User

Normal users have limited permissions.

User IDs:

```text
1000+
```

They cannot modify important system files without permission.


# 🔐 sudo Command

`sudo` means:

```
SuperUser DO
```

It allows normal users to execute commands with administrator privileges.


Syntax:

```bash
sudo command
```


Example:

```bash
sudo apt update
```


Without sudo:

```bash
apt update
```

May show:

```text
Permission denied
```


With sudo:

```bash
sudo apt update
```

The command runs with root privileges.


# ➕ Creating Users

Linux provides two common commands:

- adduser
- useradd


# 🟢 adduser

`adduser` is a user-friendly command that creates users interactively.


Example:

```bash
sudo adduser john
```


It automatically:

- Creates home directory.
- Sets password.
- Creates user information.


# 🔵 useradd

`useradd` is a lower-level command.

Example:

```bash
sudo useradd john
```


It creates the user but requires additional configuration.


Example:

Create user with home directory:

```bash
sudo useradd -m john
```


Set password:

```bash
sudo passwd john
```


# ⚔️ adduser vs useradd

| adduser | useradd |
|---|---|
| Beginner friendly | Advanced |
| Interactive | Command based |
| Creates home automatically | Requires options |
| Easier | More flexible |


## ⭐ Which is Better?

For beginners:

```bash
adduser
```

For system administrators and automation:

```bash
useradd
```


# 📄 /etc/passwd File

The `/etc/passwd` file stores information about users.

View it:

```bash
cat /etc/passwd
```


Example:

```text
john:x:1001:1001:John:/home/john:/bin/bash
```


Structure:

```text
username : password : UID : GID : comment : home : shell
```


# 🔒 /etc/shadow File

The `/etc/shadow` file stores encrypted password information.

View:

```bash
sudo cat /etc/shadow
```


Example:

```text
john:$6$randomhash:...
```


Only root users can access this file.


Why?

Because storing passwords openly would create a major security risk.


# 👑 Accessing Root User

There are different ways to access root.


## Method 1: sudo

Run individual commands:

```bash
sudo command
```


Example:

```bash
sudo nano /etc/hosts
```


## Method 2: Switch to Root

Command:

```bash
sudo su
```


Output:

```text
root@linux#
```


Now commands run as root.


## Method 3: Login as Root

```bash
su root
```


Requires the root password.


# ⚠️ Root Security

Using root gives complete control over the system.

Best practices:

✅ Use normal user accounts daily.  
✅ Use sudo when required.  
✅ Avoid running everything as root.  
✅ Protect root passwords.


