# 📘 Lecture 07: Conditional Statements in Python

Welcome to the Python Summer Camp Class 07!

In this lecture, we will learn about **Conditional Statements** in Python.

Conditional statements help programs make decisions.

They allow Python to check conditions and decide:

```text
Which code should run
and
Which code should not run
```

Conditional statements are one of the most important concepts in programming because almost every real-world application uses decision-making.

---

# 📗 Conditional Statements Concepts

- What are Conditional Statements
- Syntax of Conditional Statements
- `if` Statement
- `elif` Statement
- `else` Statement
- Code Execution Flow
- Traffic Light Practical Example
- Difference Between `if` and `elif`
- Difference Between `if`, `elif`, and `else`
- Using `True` and `False` in Conditions
- Indentation in Python
- Multiple `if` Statements
- Difference Between Multiple `if` and `if elif else`
- Using Logical Operators with Conditions
- `and` Operator
- `or` Operator
- Nested Conditions

---

# 📘 What are Conditional Statements?

Conditional statements are used to execute code based on conditions.

Python checks whether a condition is:

```text
True
or
False
```

If the condition is `True`, Python runs the code.

If the condition is `False`, Python skips the code.

---

# 📙 Syntax of Conditional Statements

```python
if (condition):
    code

elif (condition):
    code

else:
    code
```

---

# 📗 How Python Checks Conditions

Python always checks conditions from:

```text
Top → Bottom
```

Execution flow:

```text
1. First Python checks if
2. If if is False, then elif checks
3. If all conditions are False, else runs
```

---

# 📘 Flow Diagram of Conditional Statements

```text
            Start
               │
               ▼
      Is if condition True?
            /       \
          Yes        No
          /           \
         ▼             ▼
   Run if block    Check elif
                         │
            Is elif condition True?
                   /        \
                 Yes         No
                 /            \
                ▼              ▼
       Run elif block    Run else block
```

---

# 📗 1. if Statement

The `if` statement is used to check the first condition.

If the condition is `True`, the code inside the `if` block runs.

---

## Syntax of if Statement

```python
if (condition):
    code
```

---

# 📘 Traffic Light Example Using if

```python
light = "red"

if (light == "red"):
    print("Stop")
```

Output:

```python
Stop
```

---

# 📙 Explanation

Python checks:

```python
(light == "red")
```

Condition result:

```python
True
```

So Python runs:

```python
print("Stop")
```

---

# 📕 Example with False Condition

```python
light = "green"

if (light == "red"):
    print("Stop")
```

Output:

```text
No Output
```

Explanation:

```text
Condition became False,
so Python skipped the if block.
```

---

# 📒 Using True in if Statement

We can also directly write:

```python
if (True):
```

This means the condition is always True.

---

## Example

```python
if (True):
    print("Python Class")
```

Output:

```python
Python Class
```

---

# 📗 Using False in if Statement

```python
if (False):
    print("Hello")
```

Output:

```text
No Output
```

Because:

```text
False condition never runs
```

---

# 📘 2. elif Statement

`elif` means:

```text
else if
```

`elif` checks another condition when the `if` condition becomes False.

---

## Syntax of elif

```python
if (condition):
    code

elif (condition):
    code
```

---

# 📙 Traffic Light Example Using elif

```python
light = "yellow"

if (light == "red"):
    print("Stop")

elif (light == "yellow"):
    print("Ready")
```

Output:

```python
Ready
```

---

# 📗 Explanation

Python first checks:

```python
(light == "red")
```

Result:

```python
False
```

Then Python moves to:

```python
(light == "yellow")
```

Result:

```python
True
```

So Python runs:

```python
print("Ready")
```

---

# 📘 Difference Between if and elif

| if | elif |
|---|---|
| Checks the first condition | Checks additional conditions |
| Runs first | Runs only if previous condition is False |
| Required in conditional statements | Optional |

---

# 📕 Multiple elif Example

```python
light = "yellow"

if (light == "red"):
    print("Stop")

elif (light == "yellow"):
    print("Ready")

elif (light == "green"):
    print("Go")

else:
    print("Invalid Traffic Light Color")
```

Output:

```python
Ready
```

---

# 📒 3. else Statement

The `else` statement runs when all conditions become False.

---

## Syntax of else

```python
if (condition):
    code

else:
    code
```

---

# 📗 Traffic Light Example Using else

```python
light = "blue"

if (light == "red"):
    print("Stop")

elif (light == "yellow"):
    print("Ready")

elif (light == "green"):
    print("Go")

else:
    print("Invalid Traffic Light Color")
```

Output:

```python
Invalid Traffic Light Color
```

---

# 📘 Explanation

Python checks:

```python
(light == "red")
```

Result:

```python
False
```

Then:

```python
(light == "yellow")
```

Result:

```python
False
```

Then:

```python
(light == "green")
```

Result:

```python
False
```

Since all conditions became False:

```python
else
```

runs automatically.

---

# 📙 Difference Between if, elif, and else

| Statement | Purpose |
|---|---|
| if | Checks the first condition |
| elif | Checks more conditions |
| else | Runs when all conditions are False |

---

# 📗 How Many Times Can We Write Them?

| Statement | Usage Limit |
|---|---|
| if | Only 1 time |
| elif | Multiple times |
| else | Only 1 time |

---

# 📘 Correct Sequence

```python
if
elif
else
```

This order is important.

---

# 📕 Indentation in Python

Python uses indentation to define blocks of code.

Indentation means:

```text
Spaces before code
```

---

## Correct Example

```python
if (True):
    print("Hello")
```

---

## Wrong Example

```python
if (True):
print("Hello")
```

Output:

```python
IndentationError
```

---

# 📒 Why Indentation is Important?

Indentation tells Python:

```text
Which code belongs inside the condition
```

Without proper indentation, Python cannot understand the code structure.

---

# 📗 Multiple if Statements

We can also write multiple separate `if` statements.

In this case:

```text
Every if condition checks independently
```

---

## Example

```python
marks = 95

if (marks >= 50):
    print("Pass")

if (marks >= 80):
    print("Grade A")

if (marks >= 90):
    print("Excellent")
```

Output:

```python
Pass
Grade A
Excellent
```

---

# 📘 Explanation

All conditions were True.

So all `if` statements ran separately.

---

# 📙 Flow of Multiple if Statements

```text
if 1 → check
if 2 → check
if 3 → check
```

Every condition runs independently.

---

# 📕 Difference Between Multiple if and if elif else

| Multiple if | if elif else |
|---|---|
| All conditions check | Stops after first True condition |
| Multiple blocks can run | Only one block runs |
| Independent conditions | Connected conditions |

---

# 📒 Example of if elif else

```python
marks = 95

if (marks >= 90):
    print("Excellent")

elif (marks >= 80):
    print("Grade A")

elif (marks >= 50):
    print("Pass")
```

Output:

```python
Excellent
```

---

# 📗 Explanation

Python found:

```python
(marks >= 90)
```

True.

So Python stopped checking further conditions.

---

# 📘 Diagram of Multiple if vs if elif else

## Multiple if

```text
Condition 1 → Run
Condition 2 → Run
Condition 3 → Run
```

---

## if elif else

```text
Condition 1 → True
        ↓
Stop Checking Further Conditions
```

---

# 📙 Using Logical Operators with Conditions

Logical operators help us combine multiple conditions.

---

# 📗 Using and Operator

The `and` operator returns True only when:

```text
Both conditions are True
```

---

## Example

```python
marks = 85
attendance = 90

if ((marks >= 80) and (attendance >= 75)):
    print("Pass")
```

Output:

```python
Pass
```

---

# 📘 Explanation

Python checks:

```python
(marks >= 80)
```

and

```python
(attendance >= 75)
```

Since both are True:

```python
Pass
```

prints.

---

# 📕 Using or Operator

The `or` operator returns True when:

```text
At least one condition is True
```

---

## Example

```python
day = "Sunday"

if ((day == "Sunday") or (day == "Saturday")):
    print("Weekend")
```

Output:

```python
Weekend
```

---

# 📒 Explanation

Python checks:

```python
(day == "Sunday")
```

Result:

```python
True
```

Since one condition is already True:

```python
or
```

returns True.

---

# 📗 Practical Grade System Example

```python
marks = 92

if (marks >= 90):
    print("Grade A+")

elif (marks >= 80):
    print("Grade A")

elif (marks >= 70):
    print("Grade B")

elif (marks >= 60):
    print("Grade C")

else:
    print("Fail")
```

Output:

```python
Grade A+
```

---

# 📘 Nested Conditions

Nested conditions mean:

```text
A condition inside another condition
```

---

## Syntax of Nested Conditions

```python
if (condition):

    if (condition):
        code
```

---

# 📙 Example of Nested Conditions

```python
age = 20
has_id = True

if (age >= 18):

    if (has_id == True):
        print("Entry Allowed")

    else:
        print("ID Required")

else:
    print("Under Age")
```

Output:

```python
Entry Allowed
```

---

# 📗 How Nested Conditions Work

Python first checks:

```python
(age >= 18)
```

If this becomes True:

then Python checks the inner condition:

```python
(has_id == True)
```

If both conditions are True:

```python
Entry Allowed
```

prints.

---

# 📘 Nested Condition Flow Diagram

```text
Check Age
    │
    ▼
Age >= 18 ?
   /    \
 Yes     No
  │       │
  ▼       ▼
Check ID  Under Age
  │
  ▼
ID True?
 /    \
Yes    No
 │      │
 ▼      ▼
Entry   ID Required
Allowed
```

---

# 📙 Final Flow of Conditional Statements

```text
if
 ↓
elif
 ↓
else
```

Python stops checking conditions as soon as it finds:

```text
True
```

Only one matching block runs.

---