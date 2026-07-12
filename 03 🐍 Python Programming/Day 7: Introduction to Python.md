# 🐍 Day 7: Introduction to Python

> 📌 **Goal:** Understand the basics of programming, learn Python fundamentals, understand why Python is important in cybersecurity, and create your first Python scripts.



# 📚 Table of Contents

1. 💻 [What is a Programming Language?](#-what-is-a-programming-language)
2. 🐍 [History of Python](#-history-of-python)
3. 🔐 [Why Python is Used in Hacking](#-why-python-is-used-in-hacking)
4. ⚙️ [Installing Python](#️-installing-python)
5. 📝 [IDE and Code Editor](#-ide-and-code-editor)
6. 📄 [Creating a Python Script File](#-creating-a-python-script-file)
7. 🖥️ [Outputs and Comments](#️-outputs-and-comments)
8. 📦 [Variables and Data Types](#-variables-and-data-types)




# 💻 What is a Programming Language?

A programming language is a way for humans to communicate with computers by writing instructions that a computer can understand and execute.

Computers only understand machine language:

```
0 1 0 1 1 0 1
```

Programming languages allow developers to write instructions using human-readable syntax.

Example:

Python:

```python
print("Hello World")
```

The computer converts this instruction into machine-level operations.


Programming languages are used to create:

- 🌐 Websites
- 📱 Mobile applications
- 💻 Desktop software
- 🎮 Games
- 🤖 Artificial Intelligence systems
- 🔐 Security tools




# 🐍 History of Python

Python is a high-level, interpreted programming language created by:

## 👨‍💻 Guido van Rossum

Python was created by Guido van Rossum and officially released in:

```
1991
```


The name "Python" was inspired by:

```
Monty Python's Flying Circus
```

a British comedy show.


Python was designed with the goal of creating a language that is:

- Simple to read.
- Easy to learn.
- Powerful.
- Flexible.




# 📅 Python Versions

## 🐍 Python 1.0

Released:

```
1994
```

Introduced basic features.




## 🐍 Python 2.0

Released:

```
2000
```

Added improvements like:

- Garbage collection.
- List comprehensions.


Python 2 reached end of life in:

```
2020
```




## 🐍 Python 3.0

Released:

```
2008
```

Python 3 is the modern version used today.


Example:

```python
print("Hello Python")
```




# 🔐 Why Python is Used in Hacking

Python is one of the most popular programming languages in cybersecurity.

Security professionals use Python because it is:

## ⚡ Easy to Learn

Python syntax is simple compared to many programming languages.


Example:

Python:

```python
print("Hello")
```

C language:

```c
printf("Hello");
```




## 🛠️ Powerful Libraries

Python has many libraries useful for security.


Examples:

| Library | Purpose |
|-|-|
| Scapy | Network packet manipulation |
| Requests | HTTP communication |
| Socket | Network programming |
| BeautifulSoup | Web scraping |
| Nmap | Network scanning |




## 🌐 Networking Automation

Python can automate network tasks.

Examples:

- Port scanners.
- Network monitoring.
- Packet analysis.
- Security testing tools.




## 🔍 Security Tool Development

Many cybersecurity tools are written in Python.

Examples:

- Vulnerability scanners.
- Exploit scripts.
- Automation tools.
- Security testing utilities.




## 🤖 Automation

Cybersecurity involves repeating many tasks.

Python can automate:

- Log analysis.
- File scanning.
- Report generation.
- Data processing.




# ⚙️ Installing Python

Python is available for:

- 🐧 Linux
- 🪟 Windows
- 🍎 macOS




# 🐧 Installing Python on Linux

Check if Python exists:

```bash
python3 --version
```


Example:

```
Python 3.12.0
```


If not installed:

```bash
sudo apt update
```

Install:

```bash
sudo apt install python3
```


Check:

```bash
python3 --version
```




# 🪟 Installing Python on Windows

Download Python from:

```
https://python.org
```


During installation:

✅ Select:

```
Add Python to PATH
```


Verify:

```bash
python --version
```




# 📝 IDE and Code Editor

A developer needs a place to write and run code.

There are two common tools:

- IDE
- Code Editor




# 🖥️ What is an IDE?

IDE stands for:

```
Integrated Development Environment
```


An IDE is a complete programming environment that contains:

- Code editor.
- Debugger.
- Compiler/interpreter.
- Project management tools.


Examples:

- PyCharm
- Visual Studio
- Eclipse




# ✏️ What is a Code Editor?

A code editor is a lightweight program used to write code.


Examples:

- Visual Studio Code
- Sublime Text
- Nano
- Vim


Advantages:

- Faster.
- Lightweight.
- Easy customization.




# ⚔️ IDE vs Code Editor

| IDE | Code Editor |
|-|-|
| Full development environment | Mainly writing code |
| More features | Lightweight |
| Uses more resources | Faster |
| Best for large projects | Best for learning and scripting |


For cybersecurity:

⭐ Recommended:

```
Visual Studio Code
```




# 📄 Creating a Python Script File

Python files use:

```
.py
```

extension.


Example:

```
hello.py
```


Create file:

```bash
touch hello.py
```


Open:

```bash
nano hello.py
```


Write:

```python
print("Hello Cyber Security")
```


Run:

```bash
python3 hello.py
```


Output:

```
Hello Cyber Security
```




# 🖥️ Outputs in Python

Output means displaying information to the user.


Python uses:

```python
print()
```


Example:

```python
print("Hello World")
```


Output:

```
Hello World
```




# 🔢 Printing Numbers

```python
print(100)
```


Output:

```
100
```




# ➕ Printing Calculations

```python
print(5 + 5)
```


Output:

```
10
```




# 📝 Printing Multiple Values

```python
name = "Kali"

print("Operating System:", name)
```


Output:

```
Operating System: Kali
```




# 💬 Comments in Python

Comments are notes written inside code.

Python ignores comments when running programs.


Comments are used for:

- Explaining code.
- Documentation.
- Making code easier to understand.




# Single Line Comment

Use:

```python
#
```


Example:

```python
# This prints a message

print("Hello")
```




# Multi-Line Comments

Python uses triple quotes:

```python
"""
This is a comment
with multiple lines
"""
```


Example:

```python
"""
Cyber Security
Python Notes
"""

print("Start")
```




# 📦 Variables and Data Types

A variable is a container used to store information.


Example:

```python
name = "Python"
```


Here:

```
name → variable

Python → value
```


Variables allow programs to store and modify data.




# Creating Variables

Example:

```python
username = "admin"

age = 20

active = True
```




# Variable Naming Rules

Valid:

```python
user_name
password123
age
```


Invalid:

```python
1name
user-name
```


Rules:

- Cannot start with a number.
- Cannot contain spaces.
- Use meaningful names.




# 🔤 Python Data Types

Python has different types of data.


Main data types:

- String
- Integer
- Float
- Boolean
- List
- Tuple
- Dictionary




# 🔤 String (str)

Stores text.


Example:

```python
name = "Kali Linux"
```


Check type:

```python
type(name)
```


Output:

```
<class 'str'>
```




# 🔢 Integer (int)

Stores whole numbers.


Example:

```python
port = 443
```




# 🔢 Float

Stores decimal numbers.


Example:

```python
version = 3.12
```




# ✅ Boolean (bool)

Stores True or False.


Example:

```python
is_admin = True
```


Values:

```
True
False
```




# 📚 List

Stores multiple values.


Example:

```python
tools = ["nmap","burpsuite","wireshark"]
```


Access:

```python
print(tools[0])
```


Output:

```
nmap
```




# 📦 Tuple

Similar to list but cannot be changed.


Example:

```python
ports = (80,443,22)
```




# 📖 Dictionary

Stores data using key-value pairs.


Example:

```python
user = {
    "name":"admin",
    "role":"root"
}
```


Access:

```python
print(user["name"])
```


Output:

```
admin
```




# 🔍 Checking Data Type

Use:

```python
type()
```


Example:

```python
x = 100

print(type(x))
```


Output:

```
<class 'int'>
```




# 🎯 Summary

In this lesson we learned:

✅ What programming languages are.  
✅ History of Python.  
✅ Why Python is important in cybersecurity.  
✅ Installing Python.  
✅ IDE and code editors.  
✅ Creating Python scripts.  
✅ Printing output.  
✅ Writing comments.  
✅ Variables and data types.

