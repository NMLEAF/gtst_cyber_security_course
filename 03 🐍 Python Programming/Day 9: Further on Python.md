# 🐍 Day 9: Further on Python


> 📌 **Goal:** In this lesson, we will go deeper into Python programming concepts. We will learn how to organize code using functions, create reusable programs using modules, understand programming paradigms, and introduce Object-Oriented Programming (OOP).



# 📚 Table of Contents

1. 🔧 [Functions](#-functions)
2. 🔁 [Recursion](#-recursion)
3. ⚡ [Lambda Functions](#-lambda-functions)
4. 🗺️ [Map and Filter Functions](#️-map-and-filter-functions)
5. 🏗️ [POP and OOP](#️-pop-and-oop)
6. 📦 [Classes and Objects](#-classes-and-objects)
7. 🧩 [User-Built Modules](#-user-built-modules)



# 🔧 Functions

## What is a Function?

A function is a reusable block of code that performs a specific task.

Instead of writing the same code many times, we create a function once and reuse it.



## Creating a Function

Syntax:

```python
def function_name():
    # code block
```

Example:

```python
def greet():
    print("Hello Python")

greet()
```

Output:

```
Hello Python
```



# Function with Parameters

Parameters allow functions to receive information.

Example:

```python
def greet(name):
    print("Hello", name)


greet("Nathan")
```

Output:

```
Hello Nathan
```

Here:

```
name → Parameter

"Nathan" → Argument
```



# Multiple Parameters

```python
def add(a, b):
    result = a + b
    print(result)


add(10, 20)
```

Output:

```
30
```



# Returning Values

Functions can return results using `return`.

Example:

```python
def multiply(a, b):
    return a * b


answer = multiply(5, 4)

print(answer)
```

Output:

```
20
```



# 🔁 Recursion

## What is Recursion?

Recursion is a process where a function calls itself.

A recursive function must have:

1. Base condition → stops recursion
2. Recursive call → calls itself again



## Example: Countdown

```python
def countdown(number):

    if number == 0:
        print("Finished")
        return

    print(number)

    countdown(number - 1)


countdown(5)
```

Output:

```
5
4
3
2
1
Finished
```



# Example: Factorial Using Recursion

Factorial:

```
5! = 5 × 4 × 3 × 2 × 1
```

Code:

```python
def factorial(n):

    if n == 1:
        return 1

    return n * factorial(n-1)


print(factorial(5))
```

Output:

```
120
```



# ⚡ Lambda Functions

## What is Lambda?

A lambda function is a small anonymous function.

It does not have a name.

Syntax:

```python
lambda arguments : expression
```



## Normal Function

```python
def square(x):
    return x * x
```

Lambda version:

```python
square = lambda x: x * x

print(square(5))
```

Output:

```
25
```



# Multiple Arguments in Lambda

```python
add = lambda a,b: a+b

print(add(10,20))
```

Output:

```
30
```



# 🗺️ Map Function

The `map()` function applies a function to every item in an iterable.

Syntax:

```python
map(function, iterable)
```

Example:

```python
numbers = [1,2,3,4,5]

result = map(lambda x:x*2, numbers)

print(list(result))
```

Output:

```
[2,4,6,8,10]
```



# Filter Function

The `filter()` function selects items based on a condition.

Syntax:

```python
filter(function, iterable)
```

Example:

```python
numbers = [1,2,3,4,5,6]

even = filter(lambda x:x%2==0, numbers)

print(list(even))
```

Output:

```
[2,4,6]
```



# 🏗️ POP and OOP

Python supports different programming approaches.



# POP (Procedure-Oriented Programming)

POP focuses on:

- Functions
- Procedures
- Step-by-step instructions

Example languages:

- C
- Pascal

Example:

```python
def calculate_area(length,width):

    return length * width


print(calculate_area(5,4))
```



# OOP (Object-Oriented Programming)

OOP focuses on:

- Objects
- Classes
- Data and behavior together

Examples:

- Python
- Java
- C++



## Difference Between POP and OOP

| POP | OOP |
|-|-|
| Focuses on functions | Focuses on objects |
| Data is separated | Data and methods are combined |
| Less reusable | Highly reusable |
| Good for small programs | Good for large systems |



# 📦 Classes and Objects

## What is a Class?

A class is a blueprint for creating objects.

Example:

```python
class Student:
    pass
```



## What is an Object?

An object is an instance of a class.

Example:

```python
class Student:
    pass


student1 = Student()

print(student1)
```



# Class Attributes

```python
class Student:

    school = "ABC School"


student1 = Student()

print(student1.school)
```

Output:

```
ABC School
```



# Constructor (`__init__`)

The constructor runs automatically when an object is created.

Example:

```python
class Student:

    def __init__(self,name,age):
        self.name = name
        self.age = age


student1 = Student("Nathan",22)

print(student1.name)
print(student1.age)
```

Output:

```
Nathan
22
```



# Methods in Classes

Methods are functions inside a class.

Example:

```python
class Student:

    def __init__(self,name):
        self.name = name


    def display(self):
        print("Student:",self.name)



student = Student("Nathan")

student.display()
```

Output:

```
Student: Nathan
```



# 🧩 User-Built Modules

## What is a Module?

A module is a Python file containing functions, variables, and classes.

Modules help organize large programs.



# Creating Your Own Module

Create a file:

```
calculator.py
```

Inside:

```python
def add(a,b):
    return a+b


def subtract(a,b):
    return a-b
```



Create another file:

```
main.py
```

Import the module:

```python
import calculator


print(calculator.add(10,5))
print(calculator.subtract(10,5))
```

Output:

```
15
5
```



# Import Specific Functions

```python
from calculator import add


print(add(5,3))
```

Output:

```
8
```



# Module Structure Example

```
Project
│
├── main.py
│
└── calculator.py
```



