# 📘 Lecture 12: Modules in Python
## 📦 Understanding and Using Modules

Welcome to Python Summer Camp Class 12!

In this lecture, we will learn about **Modules** in Python.

Modules help us use pre-written code and make our programs more powerful without writing everything from scratch!

---

# 🎯 What We Will Learn

- What is a Module
- Why We Need Modules
- Types of Modules
- How to Import Modules
- Built-in Modules (math, random, turtle)
- Third-Party Modules
- Creating Our Own User-Defined Modules

---

# 📦 What is a Module?

## Definition

A **Module** is a file containing Python code (functions, variables, classes) that we can use in our programs.

### Simple Definition

Think of a module like a **toolbox**:
- Just like a toolbox contains different tools (hammer, screwdriver, etc.)
- A module contains different functions and features that we can use

### Example

Instead of writing our own function to generate random numbers, we can use Python's `random` module which already has this feature!

---

# 🤔 Why Do We Need Modules?

## Problems Without Modules

Imagine you want to:
- Generate random numbers
- Calculate square root
- Work with dates and time
- Create graphics

You would have to write **complex code** for each of these!

## Benefits of Using Modules

✅ **Save Time** - Use ready-made code  
✅ **Avoid Errors** - Tested and reliable code  
✅ **Code Reusability** - Use same code in multiple projects  
✅ **Organization** - Keep code organized  
✅ **Less Code** - Don't reinvent the wheel  

---

# 📚 Types of Modules

Python has **3 types** of modules:

```
┌─────────────────────────────────────┐
│     Types of Python Modules         │
├─────────────────────────────────────┤
│  1. Built-in Modules                │
│  2. Third-Party Modules             │
│  3. User-Defined Modules            │
└─────────────────────────────────────┘
```

Let's understand each type in detail!

---

# 1️⃣ Built-in Modules

## What are Built-in Modules?

**Built-in modules** are modules that come **pre-installed** with Python.

### Key Points:

✅ **No installation needed** - Automatically available with Python  
✅ **Standard Library** - Part of Python's standard library  
✅ **Ready to use** - Just import and use  
✅ **Reliable** - Tested and maintained by Python team  

### How to Check if a Module is Built-in?

If you can import it without installing anything extra, it's a built-in module!

```python
import math      # Works immediately - Built-in! ✅
import random    # Works immediately - Built-in! ✅
import turtle    # Works immediately - Built-in! ✅
```

---

## Common Built-in Modules

Python comes with **many** built-in modules. Here are the most commonly used:

| Module | Purpose |
|--------|---------|
| `math` | Mathematical functions |
| `random` | Random number generation |
| `datetime` | Date and time operations |
| `os` | Operating system functions |
| `sys` | System-specific functions |
| `turtle` | Graphics and drawing |
| `json` | Working with JSON data |
| `csv` | Working with CSV files |
| `time` | Time-related functions |
| `statistics` | Statistical calculations |

---

# 📥 How to Import Modules

Before using any module, we need to **import** it.

## Method 1: Import Entire Module

```python
import math

result = math.sqrt(16)
print(result)
```

Output:
```
4.0
```

**Syntax:** `module_name.function_name()`

---

## Method 2: Import Specific Function

```python
from math import sqrt

result = sqrt(16)
print(result)
```

Output:
```
4.0
```

**Now we can use `sqrt()` directly without `math.`**

---

## Method 3: Import Multiple Functions

```python
from math import sqrt, pow, pi

print(sqrt(25))
print(pow(2, 3))
print(pi)
```

Output:
```
5.0
8.0
3.141592653589793
```

---

## Method 4: Import with Alias (Nickname)

```python
import math as m

result = m.sqrt(16)
print(result)
```

Output:
```
4.0
```

**Useful for long module names!**

---

# 🧮 Built-in Module: math

The `math` module provides mathematical functions.

## Importing math Module

```python
import math
```

## Common math Functions

### 1. `sqrt()` - Square Root

```python
import math

print(math.sqrt(25))
print(math.sqrt(16))
print(math.sqrt(2))
```

Output:
```
5.0
4.0
1.4142135623730951
```

---

### 2. `pow()` - Power

```python
import math

print(math.pow(2, 3))  # 2^3
print(math.pow(5, 2))  # 5^2
```

Output:
```
8.0
25.0
```

---

### 3. `pi` - Value of Pi

```python
import math

print(math.pi)
```

Output:
```
3.141592653589793
```

---

### 4. `floor()` and `ceil()`

**floor()** - Rounds down  
**ceil()** - Rounds up

```python
import math

print(math.floor(3.7))  # Round down
print(math.ceil(3.2))   # Round up
```

Output:
```
3
4
```

---

### 5. `factorial()` - Factorial

```python
import math

print(math.factorial(5))  # 5! = 5 × 4 × 3 × 2 × 1
```

Output:
```
120
```

---

## 📋 Summary of math Module

| Function | Description | Example |
|----------|-------------|---------|
| `sqrt(x)` | Square root | `math.sqrt(16)` → 4.0 |
| `pow(x, y)` | x to power y | `math.pow(2, 3)` → 8.0 |
| `pi` | Value of Pi | `math.pi` → 3.14159... |
| `floor(x)` | Round down | `math.floor(3.7)` → 3 |
| `ceil(x)` | Round up | `math.ceil(3.2)` → 4 |
| `factorial(x)` | Factorial | `math.factorial(5)` → 120 |

---

# 🎲 Built-in Module: random

The `random` module helps us generate random numbers and make random choices.

## Importing random Module

```python
import random
```

## Common random Functions

### 1. `randint()` - Random Integer

Generates a random integer between two numbers (inclusive).

```python
import random

number = random.randint(1, 10)
print(number)
```

This will print a random number between 1 and 10.

**Run it multiple times, you'll get different numbers!**

---

### 2. `random()` - Random Float

Generates a random float between 0.0 and 1.0.

```python
import random

number = random.random()
print(number)
```

Output (example):
```
0.7234567891234567
```

---

### 3. `choice()` - Random Choice from List

Picks a random element from a list.

```python
import random

fruits = ["apple", "mango", "banana", "orange"]
fruit = random.choice(fruits)
print(fruit)
```

Output (random):
```
mango
```

---

### 4. `shuffle()` - Shuffle a List

Randomly shuffles the elements of a list.

```python
import random

numbers = [1, 2, 3, 4, 5]
random.shuffle(numbers)
print(numbers)
```

Output (random order):
```
[3, 1, 5, 2, 4]
```

---

## 📋 Summary of random Module

| Function | Description | Example |
|----------|-------------|---------|
| `randint(a, b)` | Random integer between a and b | `random.randint(1, 10)` |
| `random()` | Random float between 0 and 1 | `random.random()` |
| `choice(list)` | Random element from list | `random.choice([1,2,3])` |
| `shuffle(list)` | Shuffle list randomly | `random.shuffle([1,2,3])` |

---

# 🐢 Built-in Module: turtle

The `turtle` module is used for creating graphics and drawings.

## Importing turtle Module

```python
import turtle
```

## Basic turtle Example

```python
import turtle

# Create a turtle
my_turtle = turtle.Turtle()

# Draw a square
my_turtle.forward(100)
my_turtle.right(90)
my_turtle.forward(100)
my_turtle.right(90)
my_turtle.forward(100)
my_turtle.right(90)
my_turtle.forward(100)

# Keep window open
turtle.mainloop()
```

**This will draw a square on screen!**

---

## Common turtle Functions

| Function | Description |
|----------|-------------|
| `forward(distance)` | Move forward |
| `backward(distance)` | Move backward |
| `right(angle)` | Turn right |
| `left(angle)` | Turn left |
| `color(color_name)` | Change color |
| `shape(shape_name)` | Change shape |
| `penup()` | Stop drawing |
| `pendown()` | Start drawing |

**We will use turtle in detail in Class 14!**

---

# 2️⃣ Third-Party Modules

## What are Third-Party Modules?

**Third-Party modules** are modules created by other programmers that we need to **install separately**.

### Key Points:

⚠️ **Not included with Python** - Need to install  
⚠️ **Use pip to install** - Python's package installer  
✅ **Powerful features** - Advanced functionality  
✅ **Community-created** - Made by developers worldwide  

---

## How to Install Third-Party Modules?

We use **pip** (Python's package installer) to install third-party modules.

### Syntax:

```bash
pip install module_name
```

---

## Examples of Third-Party Modules

### 1. pygame - Game Development

```bash
pip install pygame
```

Used for creating games with graphics and sound.

---

### 2. flask - Web Development

```bash
pip install flask
```

Used for creating websites and web applications.

---

### 3. numpy - Scientific Computing

```bash
pip install numpy
```

Used for numerical calculations and data analysis.

---

### 4. pandas - Data Analysis

```bash
pip install pandas
```

Used for working with data tables and analysis.

---

## 📋 Common Third-Party Modules

| Module | Purpose | Install Command |
|--------|---------|-----------------|
| `pygame` | Game development | `pip install pygame` |
| `flask` | Web development | `pip install flask` |
| `numpy` | Scientific computing | `pip install numpy` |
| `pandas` | Data analysis | `pip install pandas` |
| `requests` | HTTP requests | `pip install requests` |
| `pillow` | Image processing | `pip install pillow` |

---

## Difference: Built-in vs Third-Party

| Feature | Built-in Modules | Third-Party Modules |
|---------|------------------|---------------------|
| **Installation** | No installation needed | Need `pip install` |
| **Availability** | Always available | Must install first |
| **Source** | Python team | Other developers |
| **Examples** | math, random, turtle | pygame, flask, numpy |

---

# 3️⃣ User-Defined Modules

## What are User-Defined Modules?

**User-defined modules** are modules that **we create ourselves**.

### Key Points:

✅ **Custom code** - We write the functions  
✅ **Reusable** - Use in multiple programs  
✅ **Organized** - Keep related functions together  
✅ **Easy to share** - Share with other projects  

---

## How to Create a User-Defined Module?

Creating your own module is simple!

### Step 1: Create a Python File

Create a file: `my_functions.py`

```python
# my_functions.py

def greet(name):
    """Greet a person by name"""
    return f"Hello {name}!"

def add(a, b):
    """Add two numbers"""
    return a + b

def multiply(a, b):
    """Multiply two numbers"""
    return a * b

def circle_area(radius):
    """Calculate area of circle"""
    pi = 3.14159
    return pi * radius * radius
```

---

### Step 2: Import and Use It

Create another file: `main.py`

```python
# main.py

import my_functions

# Use the functions
print(my_functions.greet("Zoha"))
print(my_functions.add(5, 3))
print(my_functions.multiply(4, 5))
print(my_functions.circle_area(7))
```

Output:
```
Hello Zoha!
8
20
153.93791
```

**Congratulations! `my_functions` is your own custom module!**

---

## Why Create User-Defined Modules?

### Benefits:

✅ **Organization** - Keep related functions together  
✅ **Reusability** - Use same functions in multiple programs  
✅ **Easy to maintain** - Update in one place  
✅ **Team collaboration** - Share modules with team  

---

## Example: Calculator Module

Let's create a useful calculator module!

### Step 1: Create `calculator.py`

```python
# calculator.py

def add(a, b):
    """Add two numbers"""
    return a + b

def subtract(a, b):
    """Subtract two numbers"""
    return a - b

def multiply(a, b):
    """Multiply two numbers"""
    return a * b

def divide(a, b):
    """Divide two numbers"""
    if b == 0:
        return "Error: Cannot divide by zero"
    return a / b

def power(a, b):
    """Calculate a to the power of b"""
    return a ** b
```

---

### Step 2: Use `calculator.py`

```python
# use_calculator.py

import calculator

print("Addition:", calculator.add(10, 5))
print("Subtraction:", calculator.subtract(10, 5))
print("Multiplication:", calculator.multiply(10, 5))
print("Division:", calculator.divide(10, 5))
print("Power:", calculator.power(2, 3))
```

Output:
```
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
Power: 8
```

---

# 📊 Complete Module Types Summary

| Type | Description | Installation | Examples |
|------|-------------|--------------|----------|
| **Built-in** | Come with Python | No installation | math, random, turtle, os, datetime |
| **Third-Party** | Created by others | `pip install` needed | pygame, flask, numpy, pandas |
| **User-Defined** | You create them | No installation (you made it!) | my_functions, calculator |

---

# 📝 Practice Examples

## Example 1: Using Multiple Modules

```python
import math
import random

# Generate random number
num = random.randint(1, 100)
print(f"Random number: {num}")

# Calculate square root
sqrt_result = math.sqrt(num)
print(f"Square root: {sqrt_result}")
```

---

## Example 2: Circle Calculator Module

Create `geometry.py`:

```python
# geometry.py

import math

def circle_area(radius):
    """Calculate area of circle"""
    return math.pi * radius * radius

def circle_circumference(radius):
    """Calculate circumference of circle"""
    return 2 * math.pi * radius

def rectangle_area(length, width):
    """Calculate area of rectangle"""
    return length * width
```

Use it:

```python
import geometry

print("Circle area:", geometry.circle_area(5))
print("Circle circumference:", geometry.circle_circumference(5))
print("Rectangle area:", geometry.rectangle_area(10, 5))
```

---

# 🎓 Concepts Summary

## What We Learned

✅ What modules are and why we need them  
✅ Three types of modules:
   - Built-in (pre-installed with Python)
   - Third-Party (need pip install)
   - User-Defined (we create ourselves)
✅ How to import modules (4 different ways)  
✅ `math` module and its functions  
✅ `random` module and its functions  
✅ `turtle` module basics  
✅ How to install third-party modules  
✅ How to create our own user-defined modules  

---

# 🏆 Practice Exercises

## Exercise 1: Using Built-in Modules
Create a program that:
- Generates a random number between 1 and 100
- Calculates its square root using `math.sqrt()`
- Displays both numbers

## Exercise 2: Create Your Own Module
Create a module `student.py` with functions:
- `calculate_average(marks_list)` - Calculate average of marks
- `find_grade(average)` - Return grade based on average
- `display_result(name, average, grade)` - Display student result

Then import and use it in another file!

## Exercise 3: Explore Turtle
Use the `turtle` module to:
- Draw a triangle
- Draw a circle
- Draw your name initials

---

# 🎯 Next Lecture Preview

In **Class 13**, we will use the `random` module to create our **first game** - a **Number Guessing Game**!

Now that you understand modules, you'll be ready to:
- Import and use `random` module
- Generate random numbers
- Create an interactive game

---

**Happy Learning! 📚✨**
