# 🐧 Day 6: Finishing Linux

> 📌 **Goal:** Learn advanced Linux usage including script installation methods, Linux help systems, services, processes, symbolic links, aliases, terminal management, downloading tools, and advanced file searching using `find`.


# 📚 Table of Contents

1. 📜 [Script Installation](#-script-installation)
2. 🆘 [Getting Help in Linux](#-getting-help-in-linux)
3. ⚙️ [Linux Processes and Services](#️-linux-processes-and-services)
4. 🔄 [Managing Processes](#-managing-processes)
5. 🖥️ [Foreground and Background Processes](#️-foreground-and-background-processes)
6. 🛠️ [Managing Linux Services](#️-managing-linux-services)
7. 🚫 [Null Device and Output Redirection](#-null-device-and-output-redirection)
8. 🔗 [Symbolic Linking](#-symbolic-linking)
9. ⚡ [Linux Alias](#-linux-alias)
10. 🪟 [tmux Terminal Multiplexer](#-tmux-terminal-multiplexer)
11. 🌐 [wget Command](#-wget-command)
12. 🔎 [find Command](#-find-command)


# 📜 Script Installation

Linux programs can be installed in different ways.

Besides package managers like:

```bash
apt
dpkg
flatpak
```

some applications require installation using scripts.


Common installation methods:

- 🐙 Git
- 🐍 Python
- 🐹 Go


# 🐙 Installing Software Using Git

Git is a version control system used to download source code from repositories.

Many security tools are hosted on:

```
GitHub
```


Install Git:

```bash
sudo apt install git
```


Check version:

```bash
git --version
```


## Clone a Repository

Example:

```bash
git clone https://github.com/user/project.git
```


This creates a directory:

```text
project/
├── files
├── scripts
└── README.md
```


Move into directory:

```bash
cd project
```


Read installation instructions:

```bash
cat README.md
```


Common installation:

```bash
chmod +x install.sh
./install.sh
```


# 🐍 Installing Python-Based Tools

Python tools usually contain:

```text
requirements.txt
setup.py
main.py
```


Check Python:

```bash
python3 --version
```


Install dependencies:

```bash
pip install -r requirements.txt
```


Run Python program:

```bash
python3 main.py
```


Example:

```bash
git clone https://github.com/example/tool

cd tool

pip install -r requirements.txt

python3 tool.py
```


# 🐹 Installing Go-Based Tools

Go is a programming language commonly used for cybersecurity tools.

Check Go:

```bash
go version
```


Install Go:

```bash
sudo apt install golang
```


Install a Go tool:

```bash
go install github.com/user/tool@latest
```


Go binaries are usually stored in:

```text
~/go/bin
```


Add Go binaries to PATH:

```bash
export PATH=$PATH:$HOME/go/bin
```


# 🆘 Getting Help in Linux

Linux provides built-in documentation systems.

The main help methods are:

- `man`
- `help`


# 📖 man Command

`man` means:

```
Manual
```


It displays detailed documentation about Linux commands.


Syntax:

```bash
man command
```


Example:

```bash
man ls
```


Output includes:

- NAME
- SYNOPSIS
- DESCRIPTION
- OPTIONS
- EXAMPLES


Example:

```bash
man find
```


Shows all available options of `find`.


## Searching Inside man Pages

Inside man:

```
/keyword
```


Example:

Search for permission:

```
/permission
```


Navigation:

| Key | Action |
|-|-|
| Space | Next page |
| b | Previous page |
| q | Exit |


# 💡 help Command

`help` provides information about shell built-in commands.


Example:

```bash
help cd
```


Works with commands built into Bash:

Examples:

```bash
help echo
help history
help export
```


Difference:

| man | help |
|-|-|
| External commands | Shell commands |
| Detailed manuals | Short explanations |


# ⚙️ Linux Processes and Services

A process is a running instance of a program.

Example:

When you open Firefox:

```
Firefox program
        |
        ↓
Firefox process
```


Every process has:

- PID (Process ID)
- Owner
- Memory usage
- CPU usage


View processes:

```bash
ps
```


Detailed:

```bash
ps aux
```


Example:

```text
USER PID %CPU COMMAND

root 1 systemd
user 234 firefox
```


# 🔄 Managing Processes

## View Running Processes

Command:

```bash
ps aux
```


## Kill a Process

Syntax:

```bash
kill PID
```


Example:

```bash
kill 1234
```


Force kill:

```bash
kill -9 PID
```


## Find Process ID

Example:

```bash
pidof firefox
```


Output:

```text
1234
```


# 🖥️ top Command

`top` displays real-time system processes.


Run:

```bash
top
```


Shows:

- CPU usage
- Memory usage
- Running processes


Useful keys:

| Key | Action |
|-|-|
| q | Exit |
| k | Kill process |
| M | Sort by memory |
| P | Sort by CPU |


# 🚀 htop Command

`htop` is an improved version of top.


Install:

```bash
sudo apt install htop
```


Run:

```bash
htop
```


Advantages:

- Color interface.
- Mouse support.
- Easier process management.


# 🟢 Foreground and Background Processes

A foreground process runs directly in the terminal.


Example:

```bash
ping google.com
```


The terminal is occupied.


## Move Process to Background

Press:

```
CTRL + Z
```


Resume in background:

```bash
bg
```


Example:

```bash
ping google.com &
```


The `&` runs a command in background.


## View Background Jobs

```bash
jobs
```


Bring process back:

```bash
fg
```


# 🛠️ Managing Linux Services

Services are programs that run continuously in the background.


Examples:

- SSH server
- Web server
- Database server


Linux uses:

```text
systemd
```


# Check Service Status

Syntax:

```bash
systemctl status service
```


Example:

```bash
systemctl status ssh
```


# Start Service

```bash
sudo systemctl start service
```


Example:

```bash
sudo systemctl start apache2
```


# Stop Service

```bash
sudo systemctl stop service
```


# Restart Service

```bash
sudo systemctl restart service
```


# Enable Service at Boot

```bash
sudo systemctl enable service
```


Example:

```bash
sudo systemctl enable ssh
```


# 🚫 Null Device and Output Redirection

Linux has a special device:

```text
/dev/null
```


It is called:

```
The black hole of Linux
```


Anything sent there is deleted.


Example:

```bash
echo "hello" > /dev/null
```


No output appears.


# Redirect Errors

Example:

```bash
command 2>/dev/null
```


`2` represents:

```
stderr (error output)
```


Example:

```bash
find / -name password 2>/dev/null
```


Hides permission errors.


# 🔗 Symbolic Linking

A symbolic link is a shortcut to another file or directory.


Similar to:

```
Windows shortcut
```


Create symbolic link:

```bash
ln -s original shortcut
```


Example:

```bash
ln -s /var/www/html website
```


Check:

```bash
ls -l
```


Output:

```text
website -> /var/www/html
```


Advantages:

- Saves space.
- Provides easier access.
- Useful for configuration management.


# ⚡ Linux Alias

An alias creates shortcuts for commands.


Example:

Instead of:

```bash
clear
```

Create:

```bash
alias c='clear'
```


Now:

```bash
c
```


## View Aliases

```bash
alias
```


## Permanent Alias

Edit:

```bash
nano ~/.bashrc
```


Add:

```bash
alias ll='ls -la'
```


Reload:

```bash
source ~/.bashrc
```


# 🪟 tmux Terminal Multiplexer

tmux allows multiple terminal sessions inside one terminal.


Install:

```bash
sudo apt install tmux
```


Start:

```bash
tmux
```


## tmux Shortcuts

Prefix:

```
CTRL + B
```


Create new window:

```
CTRL+B C
```


Switch window:

```
CTRL+B N
```


Detach:

```
CTRL+B D
```


Reattach:

```bash
tmux attach
```


Useful for:

- Remote servers.
- Long-running tasks.
- Security labs.


# 🌐 wget Command

`wget` downloads files from the internet.


Syntax:

```bash
wget URL
```


Example:

```bash
wget https://example.com/file.zip
```


Download with custom name:

```bash
wget -O file.zip URL
```


Download recursively:

```bash
wget -r website.com
```


# 🔎 find Command

`find` is one of the most powerful Linux commands.

It searches for files and directories based on:

- Name
- Type
- Size
- Permission
- Owner
- Time
- Execution


Syntax:

```bash
find location options expression
```


Example:

```bash
find /home -name notes.txt
```


# 📂 Search by Name

## Exact Name

```bash
find / -name file.txt
```


## Ignore Case

```bash
find / -iname file.txt
```


Matches:

```
File.txt
FILE.TXT
file.txt
```


# 📁 Search by Type

Find files:

```bash
find /home -type f
```


Find directories:

```bash
find /home -type d
```


Types:

| Type | Meaning |
|-|-|
| f | File |
| d | Directory |
| l | Symbolic link |


# 📏 Search by Size

Find files larger than 100MB:

```bash
find / -size +100M
```


Find files smaller than 10KB:

```bash
find / -size -10k
```


Size units:

```
k → KB
M → MB
G → GB
```


# 👤 Search by Owner

Find files owned by user:

```bash
find /home -user john
```


Find files by group:

```bash
find /home -group developers
```


# 🔐 Search by Permission

Find files with permission:

```bash
find / -perm 777
```


Find SUID files:

```bash
find / -perm -4000
```


Find writable files:

```bash
find / -perm -o+w
```


# ⏰ Search by Time

Modified recently:

```bash
find /home -mtime -7
```


Meaning:

```
Modified within last 7 days
```


Accessed recently:

```bash
find /home -atime -7
```


Changed recently:

```bash
find /home -ctime -7
```


# ⚡ Execute Commands with find

Run command on results:

```bash
find . -name "*.txt" -exec cat {} \;
```


Explanation:

```
{}
→ found file

\;
→ end command
```


Example:

Delete files:

```bash
find . -name "*.tmp" -exec rm {} \;
```


# 🔥 Practical Security Examples

Find configuration files:

```bash
find /etc -name "*.conf"
```


Find passwords:

```bash
find / -name "*password*" 2>/dev/null
```


Find SUID binaries:

```bash
find / -perm -4000 2>/dev/null
```

