# 📘 Lecture 10: Loops in Python

Welcome to the Python Summer Camp Class 10!

In this lecture, we will learn about Loops in Python.

Loops are one of the most powerful features in programming because they allow us to repeat code multiple times without writing the same code again and again.

Understanding loops is essential because they help us write cleaner, shorter, and more efficient code.

---

# Loop Concepts

- What is a Loop
- Why We Need Loops
- Types of Loops in Python
- While Loop
  - Syntax
  - Iterator and Iteration
  - Variable Naming Conventions
  - Examples
  - Infinite Loops
- Break Statement
- Continue Statement
- For Loop
  - Syntax
  - For Loop with Lists
  - For Loop with Tuples
  - For Loop with Strings
- For Loop with Else
- Range Function
  - Syntax
  - Examples
- Pass Statement

---

# What is a Loop?

## Definition

A **Loop** is a programming structure that repeats a block of code multiple times until a certain condition is met.

### Simple Definition

A loop allows us to run the same code again and again without writing it multiple times.

---

# Why We Need Loops?

Let's say we want to print "Hello" 5 times on the screen.

## Without Loop

```python
print("Hello")
print("Hello")
print("Hello")
print("Hello")
print("Hello")
```

Output:

```python
Hello
Hello
Hello
Hello
Hello
```

---

## Problems with This Approach

❌ **Problem 1:** Code repetition

❌ **Problem 2:** What if we need to print "Hello" 1000 times?

❌ **Problem 3:** Hard to maintain and update

❌ **Problem 4:** Makes code longer and difficult to read

---

## Using Loops - A Better Solution

Instead of writing the same code 5 times, we can use a loop:

```python
i = 1

while i <= 5:
    print("Hello")
    i = i + 1
```

Output:

```python
Hello
Hello
Hello
Hello
Hello
```

### Benefits of Using Loops

✔ Write code once, run multiple times

✔ Easy to change (want 1000 times? Just change the condition!)

✔ Cleaner and shorter code

✔ Easy to maintain

---

# Types of Loops in Python

Python has two types of loops:

1. **While Loop**
2. **For Loop**

---

# 📗 While Loop

The **While Loop** repeats code as long as a condition is True.

## Syntax

```python
initialization

while condition:
    # code to execute
    increment/decrement
```

---

# While Loop Example: Print "Hello" 5 Times

```python
i = 1

while i <= 5:
    print("Hello")
    i = i + 1
```

Output:

```python
Hello
Hello
Hello
Hello
Hello
```

---

# 📙 Understanding While Loop Flow

Let's understand how the loop works step by step:

## Visual Flow Diagram

```
        ┌─────────────────────┐
        │   START             │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Initialize: i = 1  │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Check Condition    │
        │     i <= 5 ?        │
        └──────────┬──────────┘
                   │
           ┌───────┴────────┐
           │                │
         True             False
           │                │
           ▼                ▼
    ┌──────────────┐   ┌──────────┐
    │ Print "Hello"│   │   END    │
    └──────┬───────┘   └──────────┘
           │
           ▼
    ┌──────────────┐
    │ i = i + 1    │
    └──────┬───────┘
           │
           │
           └────────────────┐
                            │
                            ▼
           ┌────────────────┘
           │
           └─── (Go back to Condition Check)
```

---

## Step-by-Step Flow

**Step 1: Initialization**
```python
i = 1
```
We create a variable `i` and set it to 1.

**Step 2: Condition Check**
```python
while i <= 5:
```
Python checks: Is `i <= 5`? 
- If **True** → Execute the code inside the loop
- If **False** → Exit the loop

**Step 3: Execute Code**
```python
print("Hello")
```
Print "Hello" on the screen.

**Step 4: Increment**
```python
i = i + 1
```
Increase the value of `i` by 1.

**Step 5: Repeat**

Go back to Step 2 and check the condition again.

---

# 📕 Loop Iteration Table

Let's see how the loop runs:

| Iteration | Value of i | Condition (i <= 5) | Action | New Value of i |
|-----------|------------|-------------------|---------|----------------|
| 1 | 1 | True | Print "Hello" | 2 |
| 2 | 2 | True | Print "Hello" | 3 |
| 3 | 3 | True | Print "Hello" | 4 |
| 4 | 4 | True | Print "Hello" | 5 |
| 5 | 5 | True | Print "Hello" | 6 |
| 6 | 6 | False | Loop stops | - |

---

# Important Terms

## Iterator

The variable that we use to control the loop is called an **Iterator**.

```python
i = 1  # i is the iterator
```

---

## Iteration

Each time the loop runs is called one **Iteration**.

If the loop runs 5 times, we say there are **5 iterations**.

---

## Variable Naming Conventions

For iterators, we commonly use these variable names:

```python
i, j, k
```

Example:

```python
i = 1
j = 10
k = 20
```

These are just conventions. You can use any valid variable name.

---

# 📗 While Loop Example 1: Print "Hello" with Iterator

```python
i = 1

while i <= 5:
    print("Hello", i)
    i = i + 1
```

Output:

```python
Hello 1
Hello 2
Hello 3
Hello 4
Hello 5
```

---

# 📙 While Loop Example 2: Print Counting 1 to 10

```python
i = 1

while i <= 10:
    print(i)
    i = i + 1
```

Output:

```python
1
2
3
4
5
6
7
8
9
10
```

---

# 📕 While Loop Example 3: Reverse Counting 10 to 1

```python
i = 10

while i >= 1:
    print(i)
    i = i - 1
```

Output:

```python
10
9
8
7
6
5
4
3
2
1
```

---

# 📒 Infinite Loops

## What is an Infinite Loop?

An **Infinite Loop** is a loop that never stops running because its condition is always True.

## Example

```python
i = 1

while i <= 5:
    print("Hello")
    # No increment - i will always be 1
```

This loop will print "Hello" forever because:

- `i` is always 1
- `1 <= 5` is always True
- The loop never stops

---

## Why are Infinite Loops Dangerous?

⚠️ **They freeze your program**

⚠️ **They consume 100% CPU**

⚠️ **They can crash your computer**

⚠️ **You have to force-stop the program**

---

## How to Avoid Infinite Loops?

✔ Always increment or decrement the iterator

✔ Make sure the condition will eventually become False

✔ Double-check your loop before running

---

# 📗 Break Statement

## What is Break?

The **break** statement is used to exit a loop immediately, even if the loop condition is still True.

## Syntax

```python
break
```

---

## Break Example

```python
i = 1

while i <= 5:
    print(i)
    
    if i == 3:
        break
    
    i = i + 1
```

Output:

```python
1
2
3
```

---

## How Break Works

### Visual Flow Diagram

```
        ┌─────────────────────┐
        │   START             │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Initialize: i = 1  │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Check Condition    │
        │     i <= 5 ?        │
        └──────────┬──────────┘
                   │
           ┌───────┴────────┐
           │                │
         True             False
           │                │
           ▼                ▼
    ┌──────────────┐   ┌──────────┐
    │  print(i)    │   │   END    │
    └──────┬───────┘   └──────────┘
           │
           ▼
    ┌──────────────┐
    │ Check if     │
    │   i == 3 ?   │
    └──────┬───────┘
           │
      ┌────┴─────┐
      │          │
    True       False
      │          │
      ▼          ▼
  ┌───────┐  ┌──────────┐
  │ BREAK │  │ i = i + 1│
  │       │  └─────┬────┘
  └───┬───┘        │
      │            │
      ▼            │
  ┌───────┐        │
  │  END  │        │
  └───────┘        │
                   │
                   └──────┐
                          │
                          ▼
         ┌────────────────┘
         │
         └─── (Go back to Condition Check)
```

---

### Step-by-Step Execution

1. Loop starts with `i = 1`
2. Print 1, check condition, increment to 2
3. Print 2, check condition, increment to 3
4. Print 3, check condition → `i == 3` is True
5. **break** statement executes
6. Loop stops immediately

---

## Important Point

When `break` executes:

- The loop stops immediately
- Python jumps out of the loop
- Code after the loop continues

---

# 📙 Continue Statement

## What is Continue?

The **continue** statement skips the current iteration and moves to the next iteration of the loop.

## Syntax

```python
continue
```

---

## Continue Example 1: Skip Number 3

```python
i = 1

while i <= 5:
    if i == 3:
        i = i + 1
        continue
    
    print(i)
    i = i + 1
```

Output:

```python
1
2
4
5
```

---

## How Continue Works

### Visual Flow Diagram

```
        ┌─────────────────────┐
        │   START             │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Initialize: i = 1  │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │  Check Condition    │
        │     i <= 5 ?        │
        └──────────┬──────────┘
                   │
           ┌───────┴────────┐
           │                │
         True             False
           │                │
           ▼                ▼
    ┌──────────────┐   ┌──────────┐
    │ Check if     │   │   END    │
    │   i == 3 ?   │   └──────────┘
    └──────┬───────┘
           │
      ┌────┴─────┐
      │          │
    True       False
      │          │
      ▼          ▼
  ┌───────────┐  ┌──────────┐
  │ i = i + 1 │  │ print(i) │
  └─────┬─────┘  └─────┬────┘
        │              │
        ▼              ▼
  ┌───────────┐  ┌──────────┐
  │ CONTINUE  │  │ i = i + 1│
  │ (Skip to  │  └─────┬────┘
  │ Condition)│        │
  └─────┬─────┘        │
        │              │
        └──────┬───────┘
               │
               ▼
      ┌────────────────┘
      │
      └─── (Go back to Condition Check)
```

---

### Step-by-Step Execution

1. When `i == 3`, the condition becomes True
2. `continue` is executed
3. Loop skips `print(i)` for that iteration
4. Loop goes back to check the condition
5. Next iteration starts with `i = 4`

---

## Continue Example 2: Print Only Even Numbers

```python
i = 1

while i <= 10:
    if i % 2 != 0:  # If i is odd
        i = i + 1
        continue
    
    print(i)  # This only runs for even numbers
    i = i + 1
```

Output:

```python
2
4
6
8
10
```

---

## Important Note

**continue** only skips the current iteration.

**break** stops the entire loop.

---

# 📕 For Loop

## What is a For Loop?

A **For Loop** is used to iterate over a sequence (list, tuple, string, etc.).

### When to Use For Loop?

Use for loop when:

✔ You want to iterate over a list, tuple, or string

✔ You know how many times you need to loop

✔ You want to access each element in a collection

---

## For Loop Syntax

```python
for variable in sequence:
    # code to execute
```

Here:

- `variable` = Iterator variable (takes each value from the sequence)
- `sequence` = List, tuple, string, or range

---

# For Loop with List

```python
fruits = ["Apple", "Mango", "Banana", "Orange"]

for fruit in fruits:
    print(fruit)
```

Output:

```python
Apple
Mango
Banana
Orange
```

---

## How For Loop Works with List

### Visual Flow Diagram

```
        ┌─────────────────────────────┐
        │         START               │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │  Initialize Sequence        │
        │  fruits = ["Apple",         │
        │  "Mango", "Banana",         │
        │  "Orange"]                  │
        └──────────┬──────────────────┘
                   │
                   ▼
        ┌─────────────────────────────┐
        │  Any Element Left           │
        │  in Sequence?               │
        └──────────┬──────────────────┘
                   │
           ┌───────┴────────┐
           │                │
         Yes              No
           │                │
           ▼                ▼
    ┌──────────────┐   ┌──────────┐
    │ Assign Next  │   │   END    │
    │ Element to   │   └──────────┘
    │ Variable     │
    │ fruit        │
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │ Execute Code │
    │ print(fruit) │
    └──────┬───────┘
           │
           │
           └────────────────┐
                            │
                            ▼
           ┌────────────────┘
           │
           └─── (Go back to check next element)
```

---

### Step-by-Step Execution

1. First iteration: `fruit = "Apple"`, print "Apple"
2. Second iteration: `fruit = "Mango"`, print "Mango"
3. Third iteration: `fruit = "Banana"`, print "Banana"
4. Fourth iteration: `fruit = "Orange"`, print "Orange"
5. Loop ends (no more elements)

---

# For Loop with Tuple

```python
numbers = (10, 20, 30, 40, 50)

for number in numbers:
    print(number)
```

Output:

```python
10
20
30
40
50
```

---

# For Loop with String

```python
name = "Python"

for letter in name:
    print(letter)
```

Output:

```python
P
y
t
h
o
n
```

---

## Important Point

For loop automatically:

✔ Takes each element from the sequence

✔ Assigns it to the variable

✔ Stops when all elements are processed

---

# 📗 For Loop with Else

The **else** block in a for loop is optional.

## Syntax

```python
for variable in sequence:
    # code to execute
else:
    # code to execute after loop completes
```

---

## Example: For Loop with Else

```python
fruits = ["Apple", "Mango", "Banana"]

for fruit in fruits:
    print(fruit)
else:
    print("All fruits printed!")
```

Output:

```python
Apple
Mango
Banana
All fruits printed!
```

---

## When to Use Else?

Use `else` when:

✔ You want to confirm the loop completed successfully

✔ You want to run code only if the loop was **not interrupted by break**

---

## Else vs Printing Outside Loop

### Printing Outside Loop

```python
for i in range(5):
    if i == 3:
        break
    print(i)

print("Loop ended")
```

Output:

```python
0
1
2
Loop ended
```

**Note:** "Loop ended" prints even when break is used.

---

### Using Else Block

```python
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("Loop completed without break")
```

Output:

```python
0
1
2
```

**Note:** The else block does **not** execute because break was used.

---

## Key Difference

| Printing Outside Loop | Printing in Else Block |
|-----------------------|------------------------|
| Always executes | Only executes if loop completes fully |
| Runs even if break is used | Does NOT run if break is used |

---

# 📙 Range Function

## What is Range?

The **range()** function generates a sequence of numbers.

## Syntax

```python
range(start, stop, step)
```

Parameters:

- `start` = Starting number (optional, default is 0)
- `stop` = Ending number (required, stops before this number)
- `step` = Increment value (optional, default is 1)

---

## Important Points

✔ `start` is **optional** (default = 0)

✔ `stop` is **required**

✔ `step` is **optional** (default = 1)

✔ Range stops **before** the stop value (does not include it)

---

# Range Example 1: One Parameter (Stop Only)

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

**Explanation:**

- Start = 0 (default)
- Stop = 5
- Step = 1 (default)
- Prints 0, 1, 2, 3, 4 (stops before 5)

### Visual Representation

```
range(5)

Parameters:
  start = 0 (default)
  stop  = 5
  step  = 1 (default)

Generated Sequence:
┌───┬───┬───┬───┬───┐
│ 0 │ 1 │ 2 │ 3 │ 4 │ ← Stops before 5
└───┴───┴───┴───┴───┘
```

---

# Range Example 2: Two Parameters (Start, Stop)

```python
for i in range(2, 7):
    print(i)
```

Output:

```python
2
3
4
5
6
```

**Explanation:**

- Start = 2
- Stop = 7
- Step = 1 (default)
- Prints 2, 3, 4, 5, 6 (stops before 7)

### Visual Representation

```
range(2, 7)

Parameters:
  start = 2
  stop  = 7
  step  = 1 (default)

Generated Sequence:
    ┌───┬───┬───┬───┬───┐
    │ 2 │ 3 │ 4 │ 5 │ 6 │ ← Stops before 7
    └───┴───┴───┴───┴───┘
    ↑                       
  Start                    
```

---

# Range Example 3: Three Parameters (Start, Stop, Step)

```python
for i in range(1, 10, 2):
    print(i)
```

Output:

```python
1
3
5
7
9
```

**Explanation:**

- Start = 1
- Stop = 10
- Step = 2
- Prints 1, 3, 5, 7, 9 (increments by 2, stops before 10)

### Visual Representation

```
range(1, 10, 2)

Parameters:
  start = 1
  stop  = 10
  step  = 2

Generated Sequence:
    ┌───┬───┬───┬───┬───┐
    │ 1 │ 3 │ 5 │ 7 │ 9 │ ← Stops before 10
    └───┴───┴───┴───┴───┘
    ↑   ↑   ↑   ↑   ↑
    +2  +2  +2  +2  +2  (Step = 2)
```

---

# Range Example 4: Print Even Numbers

```python
for i in range(2, 11, 2):
    print(i)
```

Output:

```python
2
4
6
8
10
```

**Explanation:**

- Start = 2 (first even number)
- Stop = 11
- Step = 2 (increment by 2 to get next even number)

---

# 📕 Pass Statement

## What is Pass?

The **pass** statement is a null operation — it does nothing when executed.

### Simple Definition

`pass` is used as a placeholder when you need a statement syntactically but don't want to execute any code.

---

## Why Use Pass?

Python does not allow empty code blocks. If you want to create a loop or condition without code inside, you must use `pass`.

---

## When to Use Pass?

✔ When you're writing code structure but haven't written the logic yet

✔ When you want to create an empty loop or function temporarily

✔ When you need a placeholder for future code

---

## Pass Example 1: In For Loop

```python
for i in range(5):
    pass  # Will add code here later
```

This runs without error but does nothing.

---

## Pass Example 2: In If-Else

```python
x = 10

if x > 5:
    pass  # Will add code here later
else:
    print("x is less than or equal to 5")
```

This is valid syntax. The if block does nothing because of `pass`.

---

## Without Pass - Error

```python
for i in range(5):
    # Empty - This will cause an error
```

Output:

```python
IndentationError: expected an indented block
```

Python expects code inside the loop. Without `pass`, it's an error.

---

## Important Point

`pass` is different from `continue`:

- **pass** = Do nothing, continue to next line
- **continue** = Skip current iteration, go to next iteration

---

# 📗 Summary Table

| Category | Topics |
|----------|--------|
| Loop Types | While Loop, For Loop |
| While Loop | Initialization, Condition, Increment/Decrement |
| Control Statements | break, continue, pass |
| For Loop Usage | Lists, Tuples, Strings |
| For Loop with Else | Executes only if loop completes without break |
| Range Function | range(stop), range(start, stop), range(start, stop, step) |
| Pass Statement | Placeholder for empty code blocks |

---

# 📙 Key Differences

## While Loop vs For Loop

| Feature | While Loop | For Loop |
|---------|-----------|----------|
| Use Case | When you don't know the number of iterations | When you know the number of iterations |
| Syntax | while condition: | for variable in sequence: |
| Iterator | Manual increment/decrement | Automatic iteration |
| Best For | Condition-based loops | Iterating over sequences |

---

## Break vs Continue vs Pass

| Statement | Purpose | Effect |
|-----------|---------|--------|
| break | Exit loop immediately | Stops entire loop |
| continue | Skip current iteration | Goes to next iteration |
| pass | Do nothing | Placeholder, continues to next line |

---

# 📘 Practice Tips

✔ Start with simple loops (print numbers 1-10)

✔ Practice both while and for loops

✔ Understand when to use break and continue

✔ Experiment with range() function

✔ Always make sure your loops will terminate (avoid infinite loops!)

---
