# 📘 Lecture 11: Functions in Python

Welcome to the Python Summer Camp Class 11!

In this lecture, we will learn about **Functions** in Python.

Functions are one of the most important concepts in programming because they help us write clean, reusable, and organized code.

Understanding functions is essential because they allow us to avoid writing the same code multiple times and make our programs more efficient and maintainable.

---

# Function Concepts

- Why We Need Functions
- What is a Function
- Function Syntax
  - Parameters
  - Arguments
  - Return Statement
- Creating and Calling Functions
- Functions with Parameters
- Functions with Return Values
- Optional Parameters and Return
- Functions Without Parameters
- Functions Without Return
- Types of Functions
  - Built-in Functions
  - User-defined Functions
- Common Built-in Functions
  - print()
  - type()
  - len()
  - range()
- Default Parameters

---

# Why We Need Functions?

Let's say we need to calculate the sum of two numbers multiple times in our program.

## Without Functions - Code Repetition Problem

```python
# First time - Calculate sum
num1 = 10
num2 = 20
sum_result = num1 + num2
print("Sum:", sum_result)

# Some other code here
print("Processing...")

# Second time - Calculate sum again
num1 = 30
num2 = 40
sum_result = num1 + num2
print("Sum:", sum_result)

# More code here
print("More processing...")

# Third time - Calculate sum again
num1 = 50
num2 = 60
sum_result = num1 + num2
print("Sum:", sum_result)
```

Output:

```python
Sum: 30
Processing...
Sum: 70
More processing...
Sum: 110
```

---

## Problems with This Approach

❌ **Problem 1:** Same code is repeated 3 times (code redundancy)

❌ **Problem 2:** Hard to maintain (if we need to change the logic, we must change it in 3 places)

❌ **Problem 3:** Makes code longer and harder to read

❌ **Problem 4:** Wastes time writing the same logic again and again

❌ **Problem 5:** A sign of a bad programmer

---

## Important Point

**Code Redundancy** means writing the same code multiple times.

A good programmer always avoids redundancy by using functions.

```text
Redundant Code = Bad Programming Practice
Reusable Code = Good Programming Practice
```

---

# What is a Function?

## Definition

A **Function** is a reusable block of code that performs a specific task.

### Simple Definition

A function is like a machine:

```text
Input → Function → Output
```

You give it input (data), it processes it, and gives you output (result).

---

## Real-World Example

Think of a function like a **calculator**:

- You press buttons (input)
- Calculator performs calculation (function logic)
- You get the result on screen (output)

---

## Benefits of Using Functions

✔ **Reusability**: Write once, use multiple times

✔ **Organization**: Makes code cleaner and easier to understand

✔ **Maintainability**: Easy to update (change logic in one place)

✔ **Reduces Errors**: Less chance of mistakes

✔ **Saves Time**: No need to write the same code again

---

# 📗 Function Syntax

## Basic Syntax

```python
def function_name(parameters):
    # function body
    # code to execute
    return output
```

### Components:

1. **def** - Keyword to define a function
2. **function_name** - Name of the function
3. **parameters** - Input variables (optional)
4. **function body** - Code inside the function
5. **return** - Sends output back (optional)

---

## Function Flow Diagram

```text
        ┌─────────────────────────────┐
        │   Define Function           │
        │   def function_name():      │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │   Function Body             │
        │   (Logic/Code)              │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │   Return Output             │
        │   (Optional)                │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │   Call Function             │
        │   function_name()           │
        └─────────────────────────────┘
```

---

# 📙 Creating Our First Function

## Simple Function Without Parameters

```python
def greet():
    print("Hello World!")
    print("Welcome to Python!")
```

---

## Calling a Function

To use a function, we need to **call** it:

```python
def greet():
    print("Hello World!")
    print("Welcome to Python!")

# Calling the function
greet()
```

Output:

```python
Hello World!
Welcome to Python!
```

---

## Important Point

**Defining** a function does not execute it.

We must **call** the function to run its code.

```python
# This only defines the function (does NOT run)
def greet():
    print("Hello")

# This calls the function (runs the code)
greet()
```

---

# 📕 Solving the Sum Problem Using Functions

Let's solve the code redundancy problem we saw earlier.

## Using Functions - Better Solution

```python
def calculate_sum(num1, num2):
    sum_result = num1 + num2
    return sum_result

# First time - Just call the function
result1 = calculate_sum(10, 20)
print("Sum:", result1)

# Some other code here
print("Processing...")

# Second time - Call the function again
result2 = calculate_sum(30, 40)
print("Sum:", result2)

# More code here
print("More processing...")

# Third time - Call the function again
result3 = calculate_sum(50, 60)
print("Sum:", result3)
```

Output:

```python
Sum: 30
Processing...
Sum: 70
More processing...
Sum: 110
```

---

## Explanation

We wrote the sum logic **only once** inside the function.

Then we **called** the function **3 times** with different values.

No code repetition! ✅

---

# 📒 Parameters and Arguments

## What are Parameters?

**Parameters** are variables listed inside the parentheses when defining a function.

They act as **input variables** that receive data.

```python
def calculate_sum(num1, num2):  # num1 and num2 are parameters
    sum_result = num1 + num2
    return sum_result
```

---

## What are Arguments?

**Arguments** are the actual values we pass to the function when calling it.

```python
calculate_sum(10, 20)  # 10 and 20 are arguments
```

---

## Parameters vs Arguments

| Parameters | Arguments |
|-----------|-----------|
| Variables in function definition | Actual values passed when calling |
| `def function(param1, param2):` | `function(value1, value2)` |
| Act as placeholders | Real data |

---

## Visual Example

```python
def add_numbers(a, b):  # a and b are PARAMETERS
    return a + b

result = add_numbers(5, 10)  # 5 and 10 are ARGUMENTS
print(result)
```

Output:

```python
15
```

**Flow:**
- Arguments `5` and `10` are passed
- Parameter `a` receives `5`
- Parameter `b` receives `10`
- Function calculates `5 + 10 = 15`
- Returns `15`

---

# 📗 Return Statement

## What is Return?

The **return** statement sends output back from the function.

```python
def multiply(a, b):
    result = a * b
    return result  # Sends result back

answer = multiply(5, 3)
print(answer)
```

Output:

```python
15
```

---

## Important Points About Return

✔ Return **stops** the function execution

✔ Code after return **does not execute**

✔ Return can send any data type (int, float, string, list, etc.)

✔ A function can have multiple return statements (but only one executes)

---

## Example: Code After Return Does Not Run

```python
def test_function():
    print("Before return")
    return 10
    print("After return")  # This will NOT execute

result = test_function()
print("Result:", result)
```

Output:

```python
Before return
Result: 10
```

Notice: "After return" never printed because return stopped the function.

---

# 📙 Functions with Multiple Parameters

We can pass as many parameters as we need.

## Example: Function with 3 Parameters

```python
def calculate_total(price, quantity, tax):
    subtotal = price * quantity
    total = subtotal + tax
    return total

final_price = calculate_total(100, 2, 20)
print("Total Price:", final_price)
```

Output:

```python
Total Price: 220
```

---

# 📕 Functions Without Parameters

Functions don't always need parameters.

## Example 1: Function Without Parameters

```python
def print_message():
    print("Welcome to Python Class!")
    print("Today we learn functions.")

print_message()
```

Output:

```python
Welcome to Python Class!
Today we learn functions.
```

---

## Example 2: Getting User Input Inside Function

```python
def get_user_info():
    name = input("Enter your name: ")
    age = input("Enter your age: ")
    print(f"Hello {name}, you are {age} years old.")

get_user_info()
```

Output:

```python
Enter your name: Zoha
Enter your age: 20
Hello Zoha, you are 20 years old.
```

---

# 📒 Functions Without Return

Not every function needs to return a value.

## Example 1: Function Without Return

```python
def display_info():
    print("Name: Zoha Khan")
    print("Course: Python")
    # No return statement

display_info()
```

Output:

```python
Name: Zoha Khan
Course: Python
```

---

## What Happens When No Return?

If a function doesn't have a return statement, it automatically returns `None`.

```python
def no_return_function():
    print("This function has no return")

result = no_return_function()
print("Result:", result)
```

Output:

```python
This function has no return
Result: None
```

---

## When to Use Return vs Print

| Use Return | Use Print |
|-----------|-----------|
| When you need the result for further calculations | When you just want to display information |
| `return result` | `print(result)` |
| Can be used in expressions | Cannot be used in expressions |

---

# 📗 Optional Input and Output

Functions have **two optional parts**:

1. **Input (Parameters)** - Optional
2. **Output (Return)** - Optional

---

## Four Types of Functions

| Type | Has Parameters? | Has Return? |
|------|----------------|-------------|
| Type 1 | ✅ Yes | ✅ Yes |
| Type 2 | ✅ Yes | ❌ No |
| Type 3 | ❌ No | ✅ Yes |
| Type 4 | ❌ No | ❌ No |

---

## Type 1: With Parameters and Return

```python
def add(a, b):
    return a + b

result = add(10, 20)
print(result)
```

Output:

```python
30
```

---

## Type 2: With Parameters, No Return

```python
def greet(name):
    print(f"Hello {name}!")

greet("Zoha")
```

Output:

```python
Hello Zoha!
```

---

## Type 3: No Parameters, With Return

```python
def get_message():
    return "Welcome to Python!"

message = get_message()
print(message)
```

Output:

```python
Welcome to Python!
```

---

## Type 4: No Parameters, No Return

```python
def show_info():
    print("This is a simple function")

show_info()
```

Output:

```python
This is a simple function
```

---

# 📙 Example: Calculate Average of Marks

Let's create a function to calculate the average of student marks.

## Example

```python
def calculate_average(mark1, mark2, mark3):
    total = mark1 + mark2 + mark3
    average = total / 3
    return average

# Calculate average for first student
student1_avg = calculate_average(85, 90, 88)
print("Student 1 Average:", student1_avg)

# Calculate average for second student
student2_avg = calculate_average(75, 80, 85)
print("Student 2 Average:", student2_avg)

# Calculate average for third student
student3_avg = calculate_average(95, 92, 98)
print("Student 3 Average:", student3_avg)
```

Output:

```python
Student 1 Average: 87.66666666666667
Student 2 Average: 80.0
Student 3 Average: 95.0
```

---

## Benefits

✔ Logic written once

✔ Used 3 times with different values

✔ Easy to maintain

✔ No code repetition

---

# 📕 Types of Functions in Python

Python has two types of functions:

1. **Built-in Functions**
2. **User-defined Functions**

---

# 1️⃣ Built-in Functions

## What are Built-in Functions?

**Built-in Functions** are functions that are already defined in Python.

We don't need to create them. We just **call** them and **pass arguments**.

---

## Common Built-in Functions

### Examples of Built-in Functions:

```python
print()
type()
len()
range()
input()
int()
float()
str()
sum()
max()
min()
```

---

# 📗 Understanding print() Function

The `print()` function has special parameters we should know about.

## Syntax

```python
print(value, sep=' ', end='\n')
```

---

## Parameter 1: sep (Separator)

The **sep** parameter defines what appears **between** multiple values.

**Default value:** `' '` (space)

### Example 1: Default Separator

```python
print("Hello", "World", "Python")
```

Output:

```python
Hello World Python
```

Notice: Space automatically appears between words.

---

### Example 2: Custom Separator

```python
print("Apple", "Mango", "Banana", sep=" | ")
```

Output:

```python
Apple | Mango | Banana
```

---

### Example 3: No Separator

```python
print("Hello", "World", sep="")
```

Output:

```python
HelloWorld
```

---

## Parameter 2: end (End Character)

The **end** parameter defines what appears **after** the print statement.

**Default value:** `'\n'` (newline - moves to next line)

### Example 1: Default End

```python
print("Hello")
print("World")
```

Output:

```python
Hello
World
```

Notice: Second print automatically starts on a new line.

---

### Example 2: Custom End

```python
print("Hello", end=" ")
print("World")
```

Output:

```python
Hello World
```

Notice: Both prints appear on the same line.

---

### Example 3: Custom End with Symbol

```python
print("Loading", end="...")
print("Done!")
```

Output:

```python
Loading...Done!
```

---

## Combining sep and end

```python
print("Python", "Java", "C++", sep=" | ", end=" <- Languages\n")
print("Done")
```

Output:

```python
Python | Java | C++ <- Languages
Done
```

---

# 📙 Other Built-in Functions

## type() Function

Returns the data type of a value.

```python
print(type(10))
print(type(10.5))
print(type("Hello"))
print(type(True))
```

Output:

```python
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
```

---

## len() Function

Returns the length of a string, list, tuple, etc.

```python
print(len("Python"))
print(len([1, 2, 3, 4, 5]))
```

Output:

```python
6
5
```

---

## range() Function

Generates a sequence of numbers.

```python
for i in range(5):
    print(i)
```

Output:

```python
0
1
2
3
4
```

---

# 2️⃣ User-defined Functions

## What are User-defined Functions?

**User-defined Functions** are functions that **we create ourselves**.

These are custom functions written by programmers to perform specific tasks.

---

## Example

```python
def calculate_square(number):
    result = number * number
    return result

answer = calculate_square(5)
print("Square:", answer)
```

Output:

```python
Square: 25
```

This is a user-defined function because **we created it**.

---

# 📗 Difference Between Built-in and User-defined Functions

| Built-in Functions | User-defined Functions |
|-------------------|------------------------|
| Already defined by Python | Created by programmers |
| Ready to use | We must define them first |
| Cannot modify them | We can modify our functions |
| Examples: print(), len(), type() | Examples: calculate_sum(), greet() |

---

# 📕 Default Parameters

## What are Default Parameters?

**Default Parameters** are parameters that have a default value.

If we don't pass an argument, the default value is used.

---

## Why Use Default Parameters?

✔ Makes functions more flexible

✔ Allows optional arguments

✔ Reduces need to pass all arguments every time

---

## Syntax

```python
def function_name(param1, param2=default_value):
    # function body
```

---

## Example 1: Multiplication with Default Parameter

```python
def multiply(a, b=2):
    result = a * b
    return result

# Calling with both arguments
print(multiply(5, 3))

# Calling with only one argument (b uses default value 2)
print(multiply(5))
```

Output:

```python
15
10
```

---

## Explanation

**First call:** `multiply(5, 3)`
- `a = 5`
- `b = 3`
- Result: `5 * 3 = 15`

**Second call:** `multiply(5)`
- `a = 5`
- `b = 2` (default value)
- Result: `5 * 2 = 10`

---

## Example 2: Greeting with Default Name

```python
def greet(name="Guest"):
    print(f"Welcome, {name}!")

greet("Zoha")
greet()
```

Output:

```python
Welcome, Zoha!
Welcome, Guest!
```

---

## Important Rule: Default Parameters Must Be at the End

**Wrong:**

```python
def wrong_function(a=10, b):  # ❌ Error
    return a + b
```

**Correct:**

```python
def correct_function(a, b=10):  # ✅ Correct
    return a + b
```

---

## Why This Rule Exists

If default parameters come first, Python cannot determine which argument goes to which parameter.

```python
# Wrong order
def test(a=5, b):
    return a + b

# How should Python interpret this?
test(10)  # Is 10 for 'a' or 'b'? Confusion!
```

**Rule:** Always place default parameters **after** non-default parameters.

---

## Example 3: Multiple Default Parameters

```python
def create_profile(name, age=18, city="Karachi"):
    print(f"Name: {name}")
    print(f"Age: {age}")
    print(f"City: {city}")

print("Profile 1:")
create_profile("Zoha", 20, "Lahore")

print("\nProfile 2:")
create_profile("Ali", 25)

print("\nProfile 3:")
create_profile("Sara")
```

Output:

```python
Profile 1:
Name: Zoha
Age: 20
City: Lahore

Profile 2:
Name: Ali
Age: 25
City: Karachi

Profile 3:
Name: Sara
Age: 18
City: Karachi
```

---

# 📗 Summary Table

| Concept | Description |
|---------|-------------|
| **Function** | Reusable block of code |
| **def** | Keyword to define a function |
| **Parameters** | Variables in function definition (input) |
| **Arguments** | Actual values passed when calling |
| **return** | Sends output back from function |
| **Built-in Functions** | Predefined functions (print, len, type) |
| **User-defined Functions** | Custom functions created by programmers |
| **Default Parameters** | Parameters with default values |

---

# 📙 Key Points to Remember

✔ Functions help avoid code redundancy

✔ Functions make code reusable and maintainable

✔ Parameters are **optional** (functions can have zero parameters)

✔ Return statement is **optional** (functions can return nothing)

✔ Functions without return automatically return `None`

✔ Default parameters must always come **after** non-default parameters

✔ Built-in functions are ready to use, user-defined functions we create ourselves

✔ `print()` has `sep` and `end` parameters for customization

✔ Always use functions to write clean, professional code

---

# 📗 Complete Example

```python
# User-defined function with default parameters
def calculate_price(quantity, price_per_item=50, discount=0):
    subtotal = quantity * price_per_item
    total = subtotal - discount
    return total

# Example 1: All arguments provided
order1 = calculate_price(5, 100, 50)
print("Order 1 Total:", order1)

# Example 2: Using default price_per_item
order2 = calculate_price(3, discount=20)
print("Order 2 Total:", order2)

# Example 3: Using all default values
order3 = calculate_price(2)
print("Order 3 Total:", order3)

# Built-in function example
print("Length of 'Python':", len("Python"))
print("Type of 100:", type(100))
```

Output:

```python
Order 1 Total: 450
Order 2 Total: 130
Order 3 Total: 100
Length of 'Python': 6
Type of 100: <class 'int'>
```

---

Happy Learning! 🎉
