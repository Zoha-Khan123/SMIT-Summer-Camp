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
- Built-in Modules (math, random)
- Module Methods and Functions
- Creating Our Own Modules

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

## 1️⃣ Built-in Modules

Modules that come **pre-installed** with Python.

**Examples:**
- `math` - Mathematical functions
- `random` - Random number generation
- `datetime` - Date and time operations
- `os` - Operating system functions

**No installation needed!** ✅

---

## 2️⃣ Standard Library Modules

More specialized modules that come with Python but need to be imported.

**Examples:**
- `turtle` - Graphics and drawing
- `tkinter` - GUI (Graphical User Interface)
- `json` - Working with JSON data
- `csv` - Working with CSV files

**No installation needed!** ✅

---

## 3️⃣ Third-Party Modules

Modules created by other programmers that we need to **install separately**.

**Examples:**
- `pygame` - Game development
- `flask` - Web development
- `numpy` - Scientific computing
- `pandas` - Data analysis

**Need to install using pip** ⚠️

```bash
pip install pygame
```

---

# 📥 How to Import Modules

There are **different ways** to import modules:

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

## Method 5: Import Everything (Not Recommended)

```python
from math import *

print(sqrt(16))
print(pow(2, 3))
```

Output:
```
4.0
8.0
```

**⚠️ Warning:** This can cause conflicts if different modules have same function names.

---

# 🧮 The `math` Module

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

# 🎲 The `random` Module

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

### 5. `uniform()` - Random Float in Range

Generates a random float between two numbers.

```python
import random

number = random.uniform(1, 10)
print(number)
```

Output (example):
```
7.234567891234567
```

---

## 📋 Summary of random Module

| Function | Description | Example |
|----------|-------------|---------|
| `randint(a, b)` | Random integer between a and b | `random.randint(1, 10)` |
| `random()` | Random float between 0 and 1 | `random.random()` |
| `choice(list)` | Random element from list | `random.choice([1,2,3])` |
| `shuffle(list)` | Shuffle list randomly | `random.shuffle([1,2,3])` |
| `uniform(a, b)` | Random float between a and b | `random.uniform(1, 10)` |

---

# 🐢 The `turtle` Module

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

**We will use turtle in detail in our next lecture!**

---

# 🔨 Creating Our Own Module

We can create our own modules too!

## Step 1: Create a Python File

Create a file: `my_functions.py`

```python
# my_functions.py

def greet(name):
    return f"Hello {name}!"

def add(a, b):
    return a + b

def multiply(a, b):
    return a * b
```

---

## Step 2: Import and Use It

Create another file: `main.py`

```python
# main.py

import my_functions

print(my_functions.greet("Zoha"))
print(my_functions.add(5, 3))
print(my_functions.multiply(4, 5))
```

Output:
```
Hello Zoha!
8
20
```

**Now `my_functions` is your own custom module!**

---

# 📝 Practice Examples

## Example 1: Random Dice Roll

```python
import random

def roll_dice():
    return random.randint(1, 6)

# Roll dice 3 times
for i in range(3):
    print(f"Roll {i+1}: {roll_dice()}")
```

Output (example):
```
Roll 1: 4
Roll 2: 2
Roll 3: 6
```

---

## Example 2: Random Password Generator

```python
import random

def generate_password(length):
    digits = "0123456789"
    password = ""
    for i in range(length):
        password += random.choice(digits)
    return password

print(generate_password(6))
```

Output (example):
```
742856
```

---

## Example 3: Circle Area Calculator

```python
import math

def circle_area(radius):
    area = math.pi * radius * radius
    return area

radius = 5
print(f"Area of circle with radius {radius}: {circle_area(radius)}")
```

Output:
```
Area of circle with radius 5: 78.53981633974483
```

---

# 🎓 Concepts Summary

## What We Learned

✅ What modules are and why we need them  
✅ Three types of modules (Built-in, Standard Library, Third-Party)  
✅ How to import modules (5 different ways)  
✅ `math` module and its functions  
✅ `random` module and its functions  
✅ Introduction to `turtle` module  
✅ How to create our own modules  

---

# 📊 Module Import Methods Summary

| Method | Syntax | Usage |
|--------|--------|-------|
| **Import Module** | `import math` | `math.sqrt(16)` |
| **Import Function** | `from math import sqrt` | `sqrt(16)` |
| **Import Multiple** | `from math import sqrt, pi` | `sqrt(16)`, `pi` |
| **Import with Alias** | `import math as m` | `m.sqrt(16)` |
| **Import All** | `from math import *` | `sqrt(16)` |

---

# 🏆 Practice Exercises

## Exercise 1: Using math Module
Write a program that:
- Takes radius as input
- Calculates area of circle using `math.pi`
- Calculates circumference

## Exercise 2: Using random Module
Write a program that:
- Generates a random number between 1 and 100
- User has 5 tries to guess it
- Give hints "Too High" or "Too Low"

## Exercise 3: Create Your Own Module
Create a module `calculator.py` with functions:
- `add(a, b)`
- `subtract(a, b)`
- `multiply(a, b)`
- `divide(a, b)`

Then import and use it in another file!

---

# 🎯 Next Lecture Preview

In the next lecture, we will use the `random` module to create our **first game** - a **Number Guessing Game**!

Now that you understand how modules work, you'll be able to:
- Import and use `random` module
- Generate random numbers
- Create an interactive game

---

**Happy Learning! 📚✨**
