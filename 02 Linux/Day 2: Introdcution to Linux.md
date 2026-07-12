# 🐧 Day 2: Introduction to Linux

## 📚 Table of Contents

1. 🐧 [What is Linux?](#-what-is-linux)
2. ⚙️ [What is Kernel?](#️-what-is-kernel)
3. 📜 [History of Linux](#-history-of-linux)
4. 🖥️ [What is an Operating System?](#️-what-is-an-operating-system)
5. 🐚 [What is Shell?](#-what-is-shell)
6. ❓ [Why Linux?](#-why-linux)
7. 📦 [Linux Distributions (Distros)](#-linux-distributions-distros)
8. 💻 [Ways to Use Linux](#-ways-to-use-linux)



# 🐧 What is Linux?

Linux is an open-source operating system kernel that is based on the UNIX design philosophy. It is widely used in servers, personal computers, smartphones, embedded devices, and cybersecurity environments.

Unlike proprietary operating systems, Linux allows users to view, modify, and distribute its source code. This makes Linux flexible, secure, and highly customizable.

Linux itself is only the **kernel**, but when combined with GNU tools and other software, it creates a complete operating system known as **GNU/Linux**.




# ⚙️ What is Kernel?

The kernel is the core component of an operating system. It acts as a bridge between hardware and software by managing communication between applications and computer resources.

The kernel is responsible for:

- 🧠 Managing CPU processes.
- 💾 Managing memory.
- 📂 Managing files and storage.
- 🔌 Controlling hardware devices.
- 🔒 Managing system security.


Example:

When you open a program, the kernel communicates with the hardware to provide the required resources.




# 📜 History of Linux

## 👨‍💻 Linus Torvalds

Linux was created by **Linus Torvalds** in 1991 while he was a university student. He developed the Linux kernel as a free and open alternative to UNIX systems.

The Linux kernel became the foundation for many operating systems used today.


## 🟣 GNU Project

In 1983, **Richard Stallman** announced the GNU Project to create a free software replacement for UNIX.

Later, in 1985, he founded the **Free Software Foundation (FSF)** to support free software development.

GNU provided many important software tools such as:

- 🐚 Bash (Shell)
- 📦 tar (Archive tool)
- ✍️ Emacs (Text editor)


However, GNU was only a collection of software tools and did not have a complete operating system kernel.

The Linux kernel provided the missing part.

Therefore:

```
GNU Tools + Linux Kernel = GNU/Linux Operating System
```


The GNU/Linux project aimed to create a UNIX-like operating system where the source code could be:

- 📖 Viewed
- ✏️ Modified
- 🔄 Redistributed




# 🖥️ What is an Operating System?

An Operating System (OS) is the main software that manages computer hardware and provides an environment where applications can run.

It acts as a connection between the user, applications, and hardware.

An operating system contains:

## ⚙️ Kernel

The core part responsible for managing hardware resources.

## 📦 Software

Applications and tools that allow users to perform tasks.

Examples:

- Web browsers
- Text editors
- Media players


## 🖼️ Desktop Environment

A desktop environment provides the graphical user interface (GUI) that users interact with.

Common Linux desktop environments:

### 🟦 GNOME
- Modern and simple interface.
- Used by many Linux distributions.

### 🟩 KDE Plasma
- Highly customizable.
- Feature-rich desktop environment.

### 🟨 XFCE
- Lightweight and fast.
- Good for older hardware.


### ⭐ Best Desktop Environment for Linux

There is no single best desktop environment.

Choice depends on your needs:

- Performance → XFCE
- Customization → KDE Plasma
- Simplicity → GNOME


## 📁 File Extensions

File extensions identify the type of file.

Examples:

```
.txt  → Text file
.jpg  → Image file
.sh   → Shell script
.py   → Python file
```

Linux does not depend heavily on extensions like Windows, but they help users identify files.


## 🪟 Window Manager

A window manager controls how application windows appear and behave on the screen.

Examples:

- i3
- Openbox
- AwesomeWM




# 🐚 What is Shell?

A shell is a program that allows users to interact with the operating system by typing commands.

It acts as a command interpreter between the user and the kernel.

Example:

```bash
ls
```

The shell sends this command to the kernel, and the system displays the result.


## 🐚 Types of Shells

### Bash (Bourne Again Shell)
- Most common Linux shell.
- Default shell in many distributions.

### Zsh (Z Shell)
- Advanced shell with customization features.
- Popular among developers.

### Fish (Friendly Interactive Shell)
- User-friendly shell.
- Provides suggestions and syntax highlighting.

### Sh (Bourne Shell)
- Original UNIX shell.
- Simple and widely supported.




# ❓ Why Linux?

Linux is popular because:

- 🔓 Open source and free.
- 🔒 Strong security.
- ⚡ Lightweight and fast.
- 🛠️ Highly customizable.
- 🌐 Powerful networking capabilities.
- 👨‍💻 Preferred by developers and cybersecurity professionals.




# 📦 Linux Distributions (Distros)

A Linux distribution is a complete operating system built using the Linux kernel combined with software packages, tools, and user interfaces.

Examples:

- 🟣 Ubuntu
- 🔴 Kali Linux
- 🔵 Fedora
- 🟢 Linux Mint
- ⚫ Arch Linux


## 🔍 How Linux Distros Differ

Distros differ based on:

- Package managers.
- Default software.
- Desktop environment.
- Security features.
- Target users.


Examples:

```
Ubuntu → Beginners
Kali Linux → Cyber Security
Arch Linux → Advanced users
Fedora → Developers
```


## 🕵️ Best Linux Distribution for Hackers

For cybersecurity learning:

### 🔴 Kali Linux

- Contains many security tools.
- Designed for penetration testing.
- Used by security professionals.

Other options:

- Parrot Security OS
- BlackArch


## 🪟 Does Windows Have Distros?

No.

Windows has different versions and editions:

Examples:

- Windows Home
- Windows Pro
- Windows Enterprise

Linux has distributions because it is open source and can be modified by different communities.




# 💻 Ways to Use Linux

Linux can be used in different ways:

## 🖥️ Main OS / Main Boot

Linux is installed as the primary operating system.

Advantages:

- Best performance.
- Full hardware access.


## 🔄 Dual Boot

Linux and another operating system are installed together.

Example:

```
Windows + Kali Linux
```

User chooses the OS during startup.


## 💿 Live Boot

Linux runs directly from a USB without installing.

Advantages:

- Portable.
- Does not modify the computer.


## ☁️ Cloud Terminals

Linux can be accessed through cloud servers.

Examples:

- Cloud virtual machines
- Online Linux terminals


## 🖥️ Virtual Machine

Linux runs inside another operating system using virtualization software.

Examples:

- VirtualBox
- VMware


Advantages:

- Safe testing environment.
- Easy to remove.


## 🪟 WSL (Windows Subsystem for Linux)

WSL allows Linux to run directly inside Windows without a traditional virtual machine.

Advantages:

- Easy setup.
- Good for development.


## 📱 Termux (Android)

Termux provides a Linux-like terminal environment on Android devices.

It allows users to run Linux commands and tools on mobile devices.


## ⭐ Best Method to Use Linux

Depends on your goal:

| Purpose | Recommended Method |
|---|---|
| Learning Linux | Virtual Machine |
| Cyber Security Practice | Virtual Machine / Dual Boot |
| Daily Linux Usage | Main OS |
| Testing Tools | Live Boot |
| Programming | WSL / Virtual Machine |
