# 🐍 Day 8: Core of Python


> 📌 **Goal:** In this lesson, we'll learn the core concepts of Python that every programmer should understand. These topics form the foundation of writing real-world Python programs.



# 📚 Table of Contents

1. 🔢 [Indexing and Slicing](#-indexing-and-slicing)
2. ⌨️ [Input Handling](#️-input-handling)
3. ➕ [Python Operators](#-python-operators)
4. 📏 [Indentation](#-indentation)
5. 🔀 [Conditional Statements](#-conditional-statements)
6. ⚠️ [Python Errors (Exceptions)](#️-python-errors-exceptions)
7. 🛡️ [Error Handling](#️-error-handling)
8. 🔁 [Loops](#-loops)



# 🔢 Indexing and Slicing

## What is Indexing?

Indexing means accessing a specific element from a sequence (such as a string, list, or tuple) using its position.

Python starts counting from **0**, not 1.

### Example

```python
name = "Python"

print(name[0])
print(name[1])
print(name[5])
```

**Output**

```
P
y
n
```



## Negative Indexing

Python also supports negative indexing.

Negative indexes start from the end.

```python
name = "Python"

print(name[-1])
print(name[-2])
print(name[-6])
```

Output

```
n
o
P
```



## Index Illustration

```
String:    P   y   t   h   o   n
Index:     0   1   2   3   4   5
Negative: -6 -5 -4 -3 -2 -1
```



# Slicing

Slicing extracts multiple elements from a sequence.

Syntax

```python
sequence[start:stop:step]
```

- start → Starting position
- stop → Ending position (not included)
- step → Interval between elements



### Example

```python
text = "Programming"

print(text[0:6])
```

Output

```
Progra
```



### Omitting Start

```python
print(text[:6])
```

Output

```
Progra
```



### Omitting Stop

```python
print(text[3:])
```

Output

```
gramming
```



### Using Step

```python
print(text[::2])
```

Output

```
Pormig
```



### Reverse a String

```python
print(text[::-1])
```

Output

```
gnimmargorP
```



# ⌨️ Input Handling

In Python, there are **two main ways to provide input to a program**:

1. 🖥️ **By using the input() function**
2. ⌨️ **By using Arguments (Command Line Arguments)**


# 1. 🖥️ Input Using `input()` Function

The `input()` function allows the program to receive information from the user while the program is running.

## Syntax

```python
variable = input("Text you like to display: ")
```

### Example

```python
name = input("Enter your name: ")

print("Hello", name)
```

Output:

```
Enter your name: Nathan

Hello Nathan
```

Explanation:

```
User enters:
Nathan

        ↓

input()

        ↓

Stored inside variable

name = "Nathan"

        ↓

print() displays the result
```


## Changing Input Data Type

By default, the `input()` function always returns data as a **string**.

Example:

```python
age = input("Enter your age: ")

print(type(age))
```

Output:

```
<class 'str'>
```

To change the input type, we use conversion functions.


## Integer Input

Using `int()`

```python
age = int(input("Enter your age: "))

print(type(age))
```

Output:

```
Enter your age: 22

<class 'int'>
```



## Float Input

Using `float()`

```python
price = float(input("Enter price: "))

print(type(price))
```

Output:

```
Enter price: 25.5

<class 'float'>
```



## String Input

Using `str()`

```python
name = str(input("Enter name: "))
```



## Eval Input

Using `eval()` allows Python to evaluate the input as a Python expression.

Example:

```python
result = eval(input("Enter calculation: "))

print(result)
```

Input:

```
10 + 5
```

Output:

```
15
```

⚠️ **Note:** `eval()` should be used carefully because it can execute Python code.



# 2. ⌨️ Input Using Arguments (Command Line Arguments)

Arguments allow us to provide input when starting the program from the command line.

Instead of asking the user during execution, we give values when running the program.



## Example

File name:

```
greet.py
```

Run:

```bash
python greet.py Nathan Hailu
```

Here:

```
python  → Python interpreter

greet.py → Program name

Nathan   → Argument 1

Hailu    → Argument 2
```



# Accessing Arguments in Python

Python stores command line arguments inside the `sys.argv` list.

First, import the `sys` module:

```python
import sys

print(sys.argv)
```

Run:

```bash
python greet.py Nathan Hailu
```

Output:

```
['greet.py', 'Nathan', 'Hailu']
```



## Example: Greeting Using Arguments

```python
import sys

name = sys.argv[1]

print("Hello", name)
```

Run:

```bash
python greet.py Nathan
```

Output:

```
Hello Nathan
```



# Multiple Arguments Example

```python
import sys

first_name = sys.argv[1]
last_name = sys.argv[2]

print("Hello", first_name, last_name)
```

Run:

```bash
python greet.py Nathan Hailu
```

Output:

```
Hello Nathan Hailu
```


# Have You Seen This Output? 🤔

Example:

Input:

```
Nathan Hailu
```

Output:

```
Hello Nathan!
```

## WHY??

Because the program received the value **Nathan** as an input and stored it inside a variable.

Example using `input()`:

```python
name = input("Enter your name: ")

print("Hello", name)
```

Process:

```
User enters:

Nathan Hailu

        ↓

input() receives the value

        ↓

name = "Nathan Hailu"

        ↓

print() uses the variable

        ↓

Hello Nathan Hailu
```

The program does not know your name automatically.

It only prints what was stored in the variable.



# Difference Between input() and Arguments

| input() Function | Arguments |
|---|---|
| Input is given while the program is running | Input is given before the program starts |
| Uses keyboard | Uses command line |
| Interactive | Automated |
| Uses `input()` | Uses `sys.argv` |
| Good for user interaction | Good for scripts and automation |



# ➕ Python Operators

Operators perform operations on values.



## Arithmetic Operators

| Operator | Meaning | Example |
|----------|----------|----------|
| + | Addition | 5 + 2 |
| - | Subtraction | 5 - 2 |
| * | Multiplication | 5 * 2 |
| / | Division | 5 / 2 |
| // | Floor Division | 5 // 2 |
| % | Modulus | 5 % 2 |
| ** | Exponent | 5 ** 2 |

Example

```python
a = 10
b = 3

print(a+b)
print(a-b)
print(a*b)
print(a/b)
print(a//b)
print(a%b)
print(a**b)
```

---

## Comparison Operators

These return **True** or **False**.

| Operator | Meaning |
|-----------|----------|
| == | Equal |
| != | Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater or Equal |
| <= | Less or Equal |

Example

```python
print(5 > 3)
print(5 == 5)
print(3 != 2)
```



## Assignment Operators

```python
x = 5
x += 2
x -= 1
x *= 3
x /= 2
```



## Logical Operators

| Operator | Meaning |
|----------|----------|
| and | Both True |
| or | One True |
| not | Reverse Boolean |

Example

```python
age = 20

print(age > 18 and age < 30)
```



## Membership Operators

```python
name = "Python"

print("P" in name)
print("A" not in name)
```



## Identity Operators

```python
a = [1,2]
b = a

print(a is b)
print(a is not b)
```



# 📏 Indentation

Python uses indentation instead of braces `{}`.

Usually, indentation is **4 spaces**.

Correct

```python
if True:
    print("Correct")
```

Wrong

```python
if True:
print("Wrong")
```

Produces

```
IndentationError
```



# Why is Indentation Important?

Indentation tells Python where a block begins and ends.

Example

```python
if 10 > 5:
    print("Inside")
    print("Still inside")

print("Outside")
```



# 🔀 Conditional Statements

Conditional statements allow programs to make decisions.



## if Statement

```python
age = 20

if age >= 18:
    print("Adult")
```



## if...else

```python
age = 15

if age >= 18:
    print("Adult")
else:
    print("Minor")
```



## if...elif...else

```python
score = 80

if score >= 90:
    print("A")

elif score >= 80:
    print("B")

elif score >= 70:
    print("C")

else:
    print("Fail")
```



## Nested if

```python
age = 20
has_id = True

if age >= 18:

    if has_id:
        print("Allowed")

    else:
        print("Need ID")

else:
    print("Too Young")
```



# ⚠️ Python Errors (Exceptions)

Errors are problems that stop a program.



## SyntaxError

```python
if True
    print("Hello")
```



## NameError

```python
print(username)
```

Variable doesn't exist.



## TypeError

```python
print(5 + "3")
```



## ValueError

```python
int("Hello")
```



## ZeroDivisionError

```python
10 / 0
```



## IndexError

```python
numbers = [1,2,3]

print(numbers[5])
```



## KeyError

```python
student = {
    "name":"John"
}

print(student["age"])
```



## ModuleNotFoundError

```python
import abcxyz
```



## FileNotFoundError

```python
open("hello.txt")
```



# 🛡️ Error Handling

Python handles errors using **try** and **except**.

Basic Example

```python
try:
    number = int(input("Number: "))
    print(number)

except:
    print("Invalid input")
```



## Handling Specific Errors

```python
try:
    number = int(input())

except ValueError:
    print("Only numbers allowed")
```



## Multiple Exceptions

```python
try:
    x = int(input())
    print(10/x)

except ValueError:
    print("Invalid Number")

except ZeroDivisionError:
    print("Cannot divide by zero")
```



## else

Runs if no exception occurs.

```python
try:
    num = int(input())

except ValueError:
    print("Invalid")

else:
    print("Everything worked!")
```



## finally

Always executes.

```python
try:
    print("Program")

finally:
    print("Finished")
```



# 🔁 Loops

Loops repeat code.



## while Loop

Runs while a condition is True.

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output

```
1
2
3
4
5
```



## Infinite Loop

```python
while True:
    print("Running")
```

Use carefully!



## for Loop

Used to iterate through sequences.

```python
for letter in "Python":
    print(letter)
```



## range()

```python
for i in range(5):
    print(i)
```

Output

```
0
1
2
3
4
```



### range(start, stop)

```python
for i in range(1,6):
    print(i)
```



### range(start, stop, step)

```python
for i in range(0,10,2):
    print(i)
```

Output

```
0
2
4
6
8
```



## break

Stops the loop.

```python
for i in range(10):

    if i == 5:
        break

    print(i)
```



## continue

Skips the current iteration.

```python
for i in range(6):

    if i == 3:
        continue

    print(i)
```



## pass

Acts as a placeholder.

```python
for i in range(5):
    pass
```