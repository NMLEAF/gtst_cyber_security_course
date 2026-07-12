# 🐧 Day 5: Advanced Linux Users

> 📌 **Goal:** Learn advanced Linux user management, permissions, special file permissions, software installation methods, and common package management errors.


# 📚 Table of Contents

1. 👥 [Advanced User Management](#-advanced-user-management)
2. 🔑 [Password Management](#-password-management)
3. 🆔 [Changing User and Group IDs](#-changing-user-and-group-ids)
4. 🗑️ [Deleting Users](#️-deleting-users)
5. 🔄 [Switching Users](#-switching-users)
6. 🏠 [Managing User Home Directory](#-managing-user-home-directory)
7. 🐚 [Changing User Shell](#-changing-user-shell)
8. 👥 [Linux Group Management](#-linux-group-management)
9. 🛡️ [Sudoers File](#️-sudoers-file)
10. 🔐 [Linux File Ownership and Permissions](#-linux-file-ownership-and-permissions)
11. ⚡ [Special File Permissions](#️-special-file-permissions)
12. 📦 [Software Installation](#-software-installation)
13. 📝 [Script Installation](#-script-installation)
14. ⚠️ [Common Package Installation Errors](#️-common-package-installation-errors)


# 👥 Advanced User Management

Linux provides powerful tools to manage users, groups, and privileges.

A Linux administrator can:

- Create users.
- Modify user information.
- Delete users.
- Assign users to groups.
- Control permissions.
- Manage system access.


# 🔑 Password Management

Every Linux user has a password used for authentication.

To change the password of a user:

```bash
sudo passwd username
```


Example:

```bash
sudo passwd john
```


Output:

```text
New password:
Retype new password:
passwd: password updated successfully
```


# 🆔 Changing User and Group IDs

Every Linux user has a unique identifier called:

```
UID (User ID)
```

Groups have:

```
GID (Group ID)
```


## Change User ID (UID)

Command:

```bash
sudo usermod -u new_id username
```


Example:

```bash
sudo usermod -u 1500 john
```


Check:

```bash
id john
```


Output:

```text
uid=1500(john)
```


## Change Group ID (GID)

Command:

```bash
sudo groupmod -g new_id groupname
```


Example:

```bash
sudo groupmod -g 2000 developers
```


# 🗑️ Deleting Users

To delete a user:

```bash
sudo userdel username
```


To delete a user and remove their home directory:

```bash
sudo userdel -r username
```


Example:

```bash
sudo userdel -r john
```


The `-r` option removes:

- User account.
- Home directory.
- User files.


# 🔄 Switching Users

Linux allows users to switch between accounts.


Command:

```bash
su - username
```


Example:

```bash
su - john
```


The `-` loads the user's complete environment.


Check current user:

```bash
whoami
```


# 🏠 Managing User Home Directory

Each Linux user normally has a home directory:

Example:

```text
/home/john
```


Sometimes a user is created without a home directory.

To create one:

```bash
sudo mkhomedir_helper username
```


Example:

```bash
sudo mkhomedir_helper john
```


Creates:

```text
/home/john
```


# 🐚 Changing User Shell

A shell is the interface used to communicate with Linux.

To change a user's default shell:

```bash
sudo usermod username -s /bin/shell
```


Example:

Change to Bash:

```bash
sudo usermod john -s /bin/bash
```


Change to Zsh:

```bash
sudo usermod john -s /bin/zsh
```


View available shells:

```bash
cat /etc/shells
```


# 👥 Linux Group Management

A group is a collection of users that share permissions.

Groups simplify permission management.

Example:

```text
Developers Group

Users:
John
Sara
Mike
```


# ➕ Creating a Group

Command:

```bash
sudo groupadd groupname
```


Example:

```bash
sudo groupadd developers
```


# 👤 Adding Users to Groups

Command:

```bash
sudo usermod -aG groupname username
```


Example:

```bash
sudo usermod -aG developers john
```


Options:

| Option | Meaning |
|---|---|
| `-a` | Append user |
| `-G` | Secondary group |


# 🔍 Checking User Groups

Command:

```bash
groups username
```


Example:

```bash
groups john
```


Output:

```text
john developers sudo
```


# ➖ Removing User From Group

Command:

```bash
sudo gpasswd -d username groupname
```


Example:

```bash
sudo gpasswd -d john developers
```


Verify:

```bash
groups john
```


# 🛡️ Sudoers File

The sudoers file controls which users can execute commands with administrator privileges.

Location:

```text
/etc/sudoers
```


A newly created user cannot automatically use:

```bash
sudo command
```

because they are not added to the sudoers configuration.


# 🔍 Accessing sudoers File

The recommended way:

```bash
sudo visudo
```


`visudo` is safer because it:

- Checks syntax errors.
- Prevents invalid configurations.


# ➕ Adding User to sudoers

Example:

```text
john ALL=(ALL:ALL) ALL
```


Meaning:

```text
john
 ↓
Can execute commands
 ↓
As root
```


After adding:

```bash
sudo apt update
```

will work for that user.


# 🔐 Linux File Ownership and Permissions

Every Linux file has three important properties:

1. Owner
2. Group
3. Permissions


Check permissions:

```bash
ls -l filename
```


Example:

```text
-rwxr-xr-- 1 john developers file.txt
```


Permission groups:

```text
Owner     Group     Others

rwx       r-x       r--
```


# 📖 Permission Types

| Permission | Symbol | Meaning |
|---|---|---|
| Read | r | View file content |
| Write | w | Modify file |
| Execute | x | Run file |


# 🔢 Permission Numbers

Linux permissions use numeric values:

| Permission | Value |
|---|---|
| Read | 4 |
| Write | 2 |
| Execute | 1 |


Example:

```bash
chmod 755 script.sh
```


Meaning:

```text
Owner  → rwx = 7
Group  → r-x = 5
Others → r-x = 5
```

# ⚡ Special File Permissions

Linux has three additional permissions besides the normal:

- Read (`r`)
- Write (`w`)
- Execute (`x`)

These are called **special permissions**.

They are commonly encountered during penetration testing and security assessments.

The three special permissions are:

1. 🔴 SUID (Set User ID)
2. 🔵 SGID (Set Group ID)
3. 🟢 Sticky Bit


# 🔴 SUID Permission (Set User ID)

SUID allows a normal user to execute a program with the permissions of the file owner.

Normally:

```text
User runs program
        ↓
Program uses user's permissions
```


With SUID:

```text
User runs program
        ↓
Program uses owner's permissions
```


Example:

If root owns a program and adds SUID:

```text
root owns program
        ↓
User executes program
        ↓
Program runs as root
```


This means the user can perform actions with root privileges without entering the sudo password.


## SUID Numeric Value

SUID adds:

```text
4000
```


Example:

```bash
chmod 4755 program
```


Breakdown:

```text
4 → SUID
7 → Owner permissions
5 → Group permissions
5 → Others permissions
```


## Finding SUID Files

Attackers and security professionals often search for SUID files:

```bash
find / -perm -4000 2>/dev/null
```


Example output:

```text
/usr/bin/passwd
/usr/bin/sudo
```


These programs can perform privileged operations.


# 🔵 SGID Permission (Set Group ID)

SGID works similarly to SUID, but it applies to groups.


For files:

The program runs with the permissions of the file group owner.


For directories:

New files created inside the directory inherit the directory group.


## SGID Numeric Value

SGID adds:

```text
2000
```


Example:

```bash
chmod 2775 shared_folder
```


Meaning:

```text
2 → SGID
7 → Owner
7 → Group
5 → Others
```


# 🟢 Sticky Bit

Sticky Bit is mainly used on directories.

It allows users to create files inside a shared directory, but only the file owner can delete or modify their own files.


Example:

The `/tmp` directory:

```bash
ls -ld /tmp
```


Output:

```text
drwxrwxrwt
```


The last `t` represents Sticky Bit.


## Sticky Bit Numeric Value

Sticky Bit adds:

```text
1000
```


Example:

```bash
chmod 1777 shared_folder
```


Meaning:

```text
1 → Sticky Bit
7 → Owner
7 → Group
7 → Others
```


# ⚔️ Special Permission Summary

| Permission | Symbol | Number | Purpose |
|---|---|---|---|
| SUID | s | 4000 | Run as file owner |
| SGID | s | 2000 | Run as group owner |
| Sticky Bit | t | 1000 | Protect files in shared folders |


# 🚨 Security Importance of Special Permissions

Special permissions are powerful because they can change normal permission behavior.

During penetration testing, security professionals check:

- Misconfigured SUID binaries.
- Dangerous root-owned programs.
- Weak permissions.

A vulnerable SUID program may allow privilege escalation.


Example:

A C program with SUID:

```c
#include <stdio.h>

int main()
{
    FILE *file;

    file = fopen("/etc/shadow", "r");

    if(file)
        printf("Successfully opened /etc/shadow file!");

    else
        printf("Unable to open /etc/shadow");

    return 0;
}
```


If root adds SUID:

```bash
chmod 4755 program
```


Any user running the program may access `/etc/shadow` using root privileges.


# 📦 Software Installation in Linux

Linux uses package managers to install, update, and remove software.

Different Linux distributions use different package systems.


Common package managers:

- 📦 dpkg
- 🚀 apt
- 🟣 flatpak


# 📦 dpkg

`dpkg` is the low-level package manager used mainly in Debian-based systems.

It installs `.deb` files directly.


Example:

```bash
sudo dpkg -i package.deb
```


Advantages:

- Direct installation of Debian packages.
- Works offline.


Disadvantages:

- Does not automatically resolve dependencies.


Example:

If a package requires another package:

```text
Package A
    |
    requires
    |
Package B
```

dpkg cannot automatically install Package B.


# 🚀 apt

`apt` is the high-level package manager for Debian-based systems.

Examples:

- Ubuntu
- Kali Linux
- Debian


Install package:

```bash
sudo apt install package_name
```


Update package list:

```bash
sudo apt update
```


Upgrade installed packages:

```bash
sudo apt upgrade
```


Remove package:

```bash
sudo apt remove package_name
```


Advantages:

- Handles dependencies automatically.
- Uses online repositories.
- Easier for users.


# 🟣 Flatpak

Flatpak is a universal Linux package system.

It allows applications to run on different Linux distributions.


Install:

```bash
flatpak install application
```


Advantages:

- Works across many distributions.
- Applications are isolated using sandboxing.


Disadvantages:

- Uses more storage.
- Sometimes slower startup.


# ⚔️ Package Manager Comparison

| Feature | dpkg | apt | flatpak |
|---|---|---|---|
| Level | Low-level | High-level | Universal |
| Dependency handling | ❌ Manual | ✅ Automatic | ✅ Automatic |
| Package type | `.deb` | Repository packages | Flatpak apps |
| Best for | Advanced users | Normal users | Desktop apps |


# ⭐ Which One is Best?

For Kali Linux:

```
apt
```

is the recommended choice.

Reasons:

- Designed for Debian systems.
- Handles dependencies.
- Easy to maintain.


Use:

```bash
sudo apt install package
```


# 📝 Script Installation

Linux programs can also be installed using scripts.

A script is a file containing commands that automate installation.


Common script types:

```text
.sh
.py
.run
```


Example:

Download script:

```bash
wget website.com/install.sh
```


Give permission:

```bash
chmod +x install.sh
```


Run:

```bash
./install.sh
```


Before running scripts:

✅ Check the source.  
✅ Understand what the script does.  
✅ Avoid unknown scripts.


# ⚠️ Common Package Installation Errors

Linux package installation may fail because of:

- Broken repositories.
- Package conflicts.
- Locked package manager.
- Missing packages.


# 🔒 Error 1: Could not get lock

Example:

```text
Could not get lock /var/lib/apt/lists/lock
```


Cause:

Another package process is running.


Solution:

Check processes:

```bash
ps aux | grep apt
```


Wait for the process to finish.


If stuck:

```bash
sudo kill process_id
```


Then:

```bash
sudo apt update
```


# 🔒 Error 2: Could not open lock

Example:

```text
Could not open lock /var/lib/dpkg/lock-frontend
```


Cause:

Another installation process is using dpkg.


Solution:

Remove lock files:

```bash
sudo rm /var/lib/dpkg/lock-frontend
sudo rm /var/lib/dpkg/lock
```


Repair packages:

```bash
sudo dpkg --configure -a
```


Then:

```bash
sudo apt update
```


# ❌ Error 3: Unable to locate package

Example:

```text
E: Unable to locate package package_name
```


Causes:

- Package list is outdated.
- Wrong package name.
- Repository missing.


Solution:

Update repositories:

```bash
sudo apt update
```


Search package:

```bash
apt search package_name
```


# 🌐 Error 4: Repository Does Not Have Release File

Example:

```text
The repository 
'http://http.kali.org/kali kali-rolling Release'
does not have a Release file
```


Causes:

- Incorrect repository configuration.
- Unsupported repository.
- Network issues.


Check repositories:

```bash
cat /etc/apt/sources.list
```


For Kali Linux, the repository should look like:

```text
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```


Update:

```bash
sudo apt update
```


# 🛡️ Best Practices for Package Management

✅ Keep repositories updated.  

```bash
sudo apt update
```

✅ Upgrade regularly.

```bash
sudo apt upgrade
```

✅ Install software from trusted sources.

✅ Avoid running unknown installation scripts.

✅ Backup important configurations.


