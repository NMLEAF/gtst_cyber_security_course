# 🐧 Day 3: Linux for Users

> 📌 **Goal:** Learn how to interact with Linux using the terminal, understand basic commands, combine commands, and manipulate text efficiently using powerful tools like `sed` and `awk`.


# 📚 Table of Contents

1. 🐉 [Overview of Kali Linux](#-overview-of-kali-linux)
2. 🐚 [The Linux Shell](#-the-linux-shell)
3. ⌨️ [Linux Command Basics](#️-linux-command-basics)
4. 🔄 [Input and Output Redirection](#-input-and-output-redirection)
5. 🔗 [Multiple Command Executions](#-multiple-command-executions)
6. 📝 [Text Manipulation in Linux](#-text-manipulation-in-linux)
7. 🔄 [sed Command](#-sed-command)
8. 📊 [awk Command](#-awk-command)
9. 🏋️ [Exercises](#️-exercises)


# 🐉 Overview of Kali Linux

Kali Linux is a Debian-based Linux distribution designed mainly for cybersecurity professionals, penetration testers, and security researchers.

It contains hundreds of pre-installed security tools used for:

- 🔍 Information gathering
- 🕵️ Vulnerability analysis
- 💥 Exploitation testing
- 🌐 Network analysis
- 🔐 Password auditing
- 🛡️ Digital forensics


## ⭐ Why Kali Linux?

Kali Linux is popular because:

- 🛠️ Comes with cybersecurity tools.
- 🐧 Based on Debian Linux.
- 🔓 Open source.
- 🌎 Widely used by security professionals.


Examples:

```text
nmap       → Network scanning
wireshark  → Network analysis
burpsuite  → Web security testing
metasploit → Exploitation framework
```


# 🐚 The Linux Shell

The Linux shell is a command-line interface that allows users to communicate with the operating system.

Instead of using graphical interfaces, users type commands to perform tasks.

Example:

```bash
ls
```

The shell receives the command, communicates with the kernel, and displays the result.


## 🐚 Popular Linux Shells

| Shell | Description |
|---|---|
| Bash | Most common Linux shell |
| Zsh | Advanced and customizable |
| Fish | Beginner friendly |
| Sh | Traditional UNIX shell |


# ⌨️ Linux Command Basics

Linux commands follow this structure:

```bash
command [options] [arguments]
```

Example:

```bash
ls -la /home
```

Meaning:

- `ls` → command
- `-la` → options
- `/home` → target


# 📂 ls — List Files

Displays files and directories.

Example:

```bash
ls
```


## Useful Options

| Option | Purpose |
|---|---|
| `-l` | Detailed information |
| `-a` | Show hidden files |
| `-h` | Human readable size |
| `-R` | Recursive listing |


Example:

```bash
ls -lah
```


# 📍 cd — Change Directory

Used to move between directories.

Example:

```bash
cd Documents
```

Go back:

```bash
cd ..
```

Go home:

```bash
cd ~
```


# 📌 pwd — Print Working Directory

Shows the current directory.

Example:

```bash
pwd
```

Output:

```text
/home/user/Documents
```


# 🖊️ echo — Display Text

Prints text or variables.

Example:

```bash
echo "Hello Linux"
```


Using variables:

```bash
name="Kali"
echo $name
```


# 🌳 tree — Directory Structure

Displays folders in a tree format.

Example:

```bash
tree
```


Limit depth:

```bash
tree -L 2
```


# 🔄 Input and Output Redirection

Linux allows users to control where data comes from and where command results go.

There are three standard streams:


| Stream | Symbol | Purpose |
|---|---|---|
| Standard Input | stdin | Data entering a command |
| Standard Output | stdout | Normal command output |
| Standard Error | stderr | Error messages |


# ➡️ Output Redirection

Output redirection sends command results into a file.


## Create or Overwrite File

```bash
echo "Linux" > file.txt
```

The `>` operator:

- Creates a file.
- Overwrites existing content.


Example:

```bash
ls > files.txt
```

Stores the output of `ls` inside `files.txt`.


## ➕ Append Output

```bash
echo "Security" >> file.txt
```

The `>>` operator:

- Adds content.
- Keeps previous data.


Example:

```bash
date >> logs.txt
```


# ⬅️ Input Redirection

Input redirection allows commands to receive input from files.

Operator:

```bash
<
```


Example:

```bash
wc -l < users.txt
```

The command reads data from `users.txt` instead of the keyboard.


## Example with cat

Normal:

```bash
cat
```

The user types input manually.


Using input redirection:

```bash
cat < file.txt
```

The file becomes the input source.


# 🔁 Combining Input and Output

Input and output can be combined.

Example:

```bash
sort < names.txt > sorted_names.txt
```


Process:

```text
names.txt
    |
    ↓
 sort command
    |
    ↓
sorted_names.txt
```


# ⚠️ Error Redirection

Errors can be redirected using:

```bash
2>
```


Example:

```bash
command 2> errors.txt
```


Redirect output and errors together:

```bash
command > output.txt 2>&1
```


Meaning:

```text
Normal Output → output.txt
Errors        → output.txt
```


# 📄 cat — Display Files

Displays file contents.

Example:

```bash
cat file.txt
```


Show line numbers:

```bash
cat -n file.txt
```


# 🔝 head — View Beginning

Shows the first lines of a file.

Example:

```bash
head file.txt
```


Show specific lines:

```bash
head -n 20 file.txt
```


# 🔚 tail — View End

Shows the last lines of a file.

Example:

```bash
tail file.txt
```


Monitor changes:

```bash
tail -f log.txt
```


# 📖 less — Read Large Files

Used for reading large files.

Example:

```bash
less file.txt
```


Controls:

```text
Space → Next page
b     → Previous page
q     → Exit
```


# ✨ touch — Create Files

Creates empty files.

Example:

```bash
touch notes.txt
```


# 📁 mkdir — Create Directory

Creates folders.

Example:

```bash
mkdir security
```


Create nested folders:

```bash
mkdir -p linux/day3
```


# 🧹 clear — Clear Terminal

Clears terminal screen.

```bash
clear
```

Shortcut:

```text
CTRL + L
```


# 🗑️ rm — Remove Files

Deletes files.

Example:

```bash
rm file.txt
```


Options:

| Option | Purpose |
|---|---|
| `-r` | Remove directories |
| `-f` | Force deletion |


Example:

```bash
rm -rf folder
```


⚠️ Deleted files are not moved to recycle bin.


# 📋 cp — Copy Files

Copies files.

Example:

```bash
cp file.txt backup.txt
```


Copy folders:

```bash
cp -r folder backup
```


# 🚚 mv — Move/Rename Files

Move:

```bash
mv file.txt Documents/
```


Rename:

```bash
mv old.txt new.txt
```


# 🔍 grep — Search Text

Searches for patterns.

Example:

```bash
grep "password" file.txt
```


Options:

| Option | Purpose |
|---|---|
| `-i` | Ignore case |
| `-r` | Recursive search |
| `-n` | Show line numbers |
| `-v` | Reverse match |


Example:

```bash
grep -rin "admin" /etc
```


# 🔢 wc — Count Data

Counts lines, words, and characters.

Example:

```bash
wc file.txt
```


Options:

| Option | Counts |
|---|---|
| `-l` | Lines |
| `-w` | Words |
| `-c` | Characters |


Example:

```bash
wc -l users.txt
```

# 🔗 Multiple Command Executions

Linux allows users to execute multiple commands together by using operators.

These operators help create powerful command workflows.


# ✅ AND Operator (`&&`)

The AND operator runs the second command only if the first command succeeds.

Syntax:

```bash
command1 && command2
```


Example:

```bash
mkdir security && cd security
```

Process:

```text
Create directory
        ↓
Enter directory
```


If `mkdir` fails, `cd` will not execute.


# ❌ OR Operator (`||`)

The OR operator runs the second command only if the first command fails.

Syntax:

```bash
command1 || command2
```


Example:

```bash
ping google.com || echo "Connection Failed"
```


Meaning:

```text
Ping succeeds
      ↓
Do nothing

Ping fails
      ↓
Display error message
```


# 🔥 Pipe Operator (`|`)

A pipe sends the output of one command as input to another command.

Syntax:

```bash
command1 | command2
```


Example:

```bash
ls -la | grep ".txt"
```


Process:

```text
ls command
    |
    ↓
List files
    |
    ↓
grep searches .txt files
```


Common examples:

Search running processes:

```bash
ps aux | grep firefox
```


Count files:

```bash
ls | wc -l
```


# 📝 Text Manipulation in Linux

Linux provides powerful tools for processing and analyzing text files.

Two important tools are:

- 🔄 sed
- 📊 awk


# 🔄 sed Command

## What is sed?

`sed` stands for **Stream Editor**.

It is a command-line text processing tool that reads text line by line and performs operations without opening the file manually.

sed is commonly used for:

- 🔍 Searching text
- 🔄 Replacing text
- 🗑️ Deleting lines
- ➕ Adding text
- ✏️ Editing files automatically


Syntax:

```bash
sed [options] 'command' file
```


Basic structure:

```bash
sed 'action' filename
```


Example:

```bash
sed 's/Linux/Kali/' file.txt
```


# 🧩 Understanding sed Syntax

The most common sed command is substitution:

```bash
s/old/new/
```


Meaning:

| Part | Meaning |
|---|---|
| `s` | substitute |
| old | text to find |
| new | replacement text |


Example:

File:

```text
I love Linux
Linux is powerful
```


Command:

```bash
sed 's/Linux/Kali/' file.txt
```


Output:

```text
I love Kali
Kali is powerful
```


# 🔥 sed Examples


## 1️⃣ Replace All Matches

By default, sed replaces only the first match in each line.

Example:

```bash
sed 's/linux/Linux/' file.txt
```


To replace every match:

```bash
sed 's/linux/Linux/g' file.txt
```


`g` means:

```text
global replacement
```


# 2️⃣ Replace Text Permanently

Normally sed only displays the result.

To modify the actual file:

```bash
sed -i 's/http/https/g' website.txt
```


Meaning:

```text
-i → edit file directly
```


# 3️⃣ Delete Lines


Delete line number 5:

```bash
sed '5d' file.txt
```


Delete lines 5-10:

```bash
sed '5,10d' file.txt
```


Delete empty lines:

```bash
sed '/^$/d' file.txt
```


Explanation:

```text
^ → beginning of line
$ → end of line
```


# 4️⃣ Print Specific Lines


Print line 5:

```bash
sed -n '5p' file.txt
```


Print lines 5-10:

```bash
sed -n '5,10p' file.txt
```


Explanation:

```text
-n → don't print automatically
p  → print selected lines
```


# 5️⃣ Insert Text


Insert before line 3:

```bash
sed '3i Hello Linux' file.txt
```


Add after line 3:

```bash
sed '3a New Line' file.txt
```


# 6️⃣ Replace Using Regular Expressions


Replace all numbers:

```bash
sed 's/[0-9]/X/g' file.txt
```


Example:

Before:

```text
Password123
```


After:

```text
PasswordXXX
```


# 📊 awk Command

## What is awk?

`awk` is a powerful text-processing language designed for analyzing structured data.

Unlike sed, which works mainly with lines, awk works mainly with:

- Columns
- Fields
- Records
- Calculations


Syntax:

```bash
awk 'pattern { action }' file
```


Example:

```bash
awk '{print $1}' users.txt
```


# 🧩 Understanding awk Fields

Example file:

```text
John 20 Linux
Sara 22 Security
Mike 21 Python
```


Fields:

```text
$1       $2       $3

John     20       Linux
Sara     22       Security
Mike     21       Python
```


Special variables:

| Variable | Meaning |
|---|---|
| `$1` | First column |
| `$2` | Second column |
| `$3` | Third column |
| `$0` | Entire line |
| `NR` | Current line number |
| `NF` | Number of fields |


# 🔥 awk Examples


# 1️⃣ Print Columns


Print usernames:

```bash
awk '{print $1}' users.txt
```


Output:

```text
John
Sara
Mike
```


Print name and language:

```bash
awk '{print $1,$3}' users.txt
```


Output:

```text
John Linux
Sara Security
Mike Python
```


# 2️⃣ Search Specific Data


Find Security:

```bash
awk '/Security/' users.txt
```


Output:

```text
Sara 22 Security
```


# 3️⃣ Print Line Numbers


Command:

```bash
awk '{print NR,$0}' users.txt
```


Output:

```text
1 John 20 Linux
2 Sara 22 Security
3 Mike 21 Python
```


# 4️⃣ Count Records


Command:

```bash
awk 'END {print NR}' users.txt
```


Output:

```text
3
```


# 5️⃣ Mathematical Operations


File:

```text
Apple 10
Orange 20
Banana 30
```


Calculate total:

```bash
awk '{sum += $2} END {print sum}' file.txt
```


Output:

```text
60
```


# 6️⃣ Conditions in awk


Print users with score greater than 80:

File:

```text
John 70
Sara 90
Mike 85
```


Command:

```bash
awk '$2 > 80 {print $1,$2}' scores.txt
```


Output:

```text
Sara 90
Mike 85
```


# ⚔️ sed vs awk

| sed | awk |
|---|---|
| Stream editor | Data processing language |
| Works line by line | Works field by field |
| Replace text | Analyze data |
| Delete lines | Perform calculations |
| Simple transformations | Complex reports |


# 🏋️ Exercises


# 🔄 sed Challenges


## 1️⃣ Replace Text

Create a file:

```text
Linux is powerful
Linux is secure
```

Replace all `Linux` with `Kali`.


Expected:

```text
Kali is powerful
Kali is secure
```


## 2️⃣ Remove Empty Lines

Given a file containing empty lines:

Remove all empty lines using sed.


Hint:

```bash
/^$/d
```


## 3️⃣ Extract Specific Lines

Print only lines 10 to 20 from:

```text
system.log
```


## 4️⃣ Hide IP Addresses

Replace IP addresses:

Before:

```text
Server IP: 192.168.1.10
```


After:

```text
Server IP: HIDDEN
```


## 5️⃣ Remove Error Messages

File:

```text
System started
error: failed login
User connected
error: timeout
```


Remove all lines containing:

```text
error
```



# 📊 awk Challenges


## 1️⃣ Print Usernames

File:

```text
John 80
Sara 90
Mike 70
```


Display only names.


Expected:

```text
John
Sara
Mike
```


## 2️⃣ Calculate Total Score

Using:

```text
John 80
Sara 90
Mike 70
```

Find the total score.


Expected:

```text
240
```


## 3️⃣ Filter High Scores

Display users with scores greater than 75.


Expected:

```text
John 80
Sara 90
```


## 4️⃣ Count Records

Count how many users exist in a file using awk.


Hint:

```bash
NR
```


## 5️⃣ Extract Linux Users

From:

```bash
/etc/passwd
```

Display only usernames.

Hint:

```bash
:
```

is the field separator.


Example:

```bash
awk -F: '{print $1}' /etc/passwd
```
