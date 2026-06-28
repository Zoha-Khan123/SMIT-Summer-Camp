# 📘 Lecture 08: Lists in Python

Welcome to the Python Summer Camp Class 08!

In this lecture, we will learn about **Lists in Python**.

Lists are one of the most important and commonly used data structures in Python.

They allow us to store multiple values inside a single variable.

Lists are very useful in real-world applications where we need to manage collections of data.

---

# 📗 List Concepts

- What is a List
- Why Lists are Used
- Creating Lists
- Data Types Stored in Lists
- Accessing List Values
- Positive Indexing
- Negative Indexing
- Updating Lists
- len() Function
- List Slicing
- Positive Slicing
- Negative Slicing
- List Methods
  - `append()`
  - `sort()`
  - `sort(reverse=True)`
  - `reverse()`
  - `insert()`
  - `remove()`
  - `pop()`

---

# 1️⃣ What is a List?

A **List** is a collection of multiple values stored inside a single variable.

Lists are written using:

```python
[ ]
```

square brackets.

---

## 📘 Example of List

```python
students = ["Zoha Khan", "Sara", "Ayesha"]
```

---

## 📙 Explanation

Here:

```python
students
```

is a list containing multiple values.

---

# 2️⃣ Why Lists are Used?

Without lists, we would need separate variables for every value.

Example without list:

```python
student1 = "Zoha Khan"
student2 = "Sara"
student3 = "Ayesha"
```

This becomes difficult when storing many values.

So Python provides lists to store multiple values together.

---

# 3️⃣ Creating Lists

## 📘 String List

```python
names = ["Zoha Khan", "Sara", "Ayesha"]
```

---

## 📙 Integer List

```python
numbers = [10, 20, 30, 40]
```

---

## 📗 Float List

```python
prices = [10.5, 20.7, 50.2]
```

---

## 📘 Boolean List

```python
status = [True, False, True]
```

---

# 4️⃣ Data Types Stored in Lists

Python lists can store:

- String
- Integer
- Float
- Boolean

and even mixed data types together.

---

## 📙 Mixed Data Type Example

```python
data = ["Zoha Khan", 20, 5.8, True]
```

Output:

```python
['Zoha Khan', 20, 5.8, True]
```

---

# 5️⃣ Accessing List Values

Lists use indexing to access values.

Index numbers start from:

```text
0
```

---

## 📘 Positive Index

| Value | Zoha Khan | Sara | Ayesha |
|---|---|---|---|
| Index | 0 | 1 | 2 |

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

print(students[0])
```

Output:

```python
Zoha Khan
```

---

# 6️⃣ Positive Indexing

Positive indexing starts from:

```text
Left → Right
```

The first value always starts from index:

```text
0
```

---

## 📘 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

print(students[1])
```

Output:

```python
Sara
```

---

# 7️⃣ Negative Indexing

Negative indexing starts from:

```text
Right → Left
```

Negative indexes start from:

```text
-1
```

---

## 📘 Negative Index

| Value | Zoha Khan | Sara | Ayesha |
|---|---|---|---|
| Index | -3 | -2 | -1 |

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

print(students[-1])
```

Output:

```python
Ayesha
```

---

## 📗 Explanation

Python starts counting from the end.

```python
-1
```

means last value.

---

# 8️⃣ Updating Lists

Lists are mutable.

Mutable means:

```text
Values inside lists can be changed.
```

---

## 📘 Example Before Updating

| Index | 0 | 1 | 2 |
|---|---|---|---|
| Value | Zoha Khan | Sara | Ayesha |

---

## 📙 Example of Updating List

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

students[1] = "Fatima"

print(students)
```

Output:

```python
['Zoha Khan', 'Fatima', 'Ayesha']
```

---

## 📗 After Updating

| Index | 0 | 1 | 2 |
|---|---|---|---|
| Value | Zoha Khan | Fatima | Ayesha |

---

# 9️⃣ len() Function

`len()` is used to find the total number of values inside a list.

---

## 📘 Syntax

```python
len(list)
```

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

print(len(students))
```

Output:

```python
3
```

---

## 📗 Explanation

The list contains:

```text
3 values
```

so `len()` returned:

```python
3
```

---

# 🔟 List Slicing

Slicing is used to get multiple values from a list.

---

## 📘 Syntax of Slicing

```python
list[start:end]
```

---

# 1️⃣1️⃣ Positive Slicing

Positive slicing starts from left to right.

---

## 📘 Positive Slicing

| Value | Zoha Khan | Sara | Ayesha | Fatima | Hira |
|---|---|---|---|---|---|
| Index | 0 | 1 | 2 | 3 | 4 |

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha", "Fatima", "Hira"]

print(students[1:4])
```

Output:

```python
['Sara', 'Ayesha', 'Fatima']
```

---

## 📗 Explanation

Python starts from index:

```python
1
```

and stops before index:

```python
4
```

---

# 1️⃣2️⃣ Negative Slicing

Negative slicing starts from right to left.

---

## 📘 Negative Slicing 

| Value | Zoha Khan | Sara | Ayesha | Fatima | Hira |
|---|---|---|---|---|---|
| Index | -5 | -4 | -3 | -2 | -1 |

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha", "Fatima", "Hira"]

print(students[-4:-1])
```

Output:

```python
['Sara', 'Ayesha', 'Fatima']
```

---

# 1️⃣3️⃣ List Methods

Methods are built-in functions used with lists.

---

# 1️⃣4️⃣ append()

`append()` adds one value at the end of the list.

---

## 📘 Syntax

```python
list.append(value)
```

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara"]

students.append("Ayesha")

print(students)
```

Output:

```python
['Zoha Khan', 'Sara', 'Ayesha']
```

---

# 1️⃣5️⃣ sort()

`sort()` arranges values in ascending order.

---

## 📘 Example

```python
numbers = [50, 10, 40, 20]

numbers.sort()

print(numbers)
```

Output:

```python
[10, 20, 40, 50]
```

---

# 1️⃣6️⃣ sort(reverse=True)

Used to sort values in descending order.

---

## 📙 Example

```python
numbers = [50, 10, 40, 20]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```python
[50, 40, 20, 10]
```

---

# 1️⃣7️⃣ reverse()

`reverse()` reverses the list order.

---

## 📘 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

students.reverse()

print(students)
```

Output:

```python
['Ayesha', 'Sara', 'Zoha Khan']
```

---

# 1️⃣8️⃣ insert()

`insert()` adds a value at a specific index position.

---

## 📙 Syntax

```python
list.insert(index, value)
```

---

## 📗 Example

```python
students = ["Zoha Khan", "Sara"]

students.insert(1, "Ayesha")

print(students)
```

Output:

```python
['Zoha Khan', 'Ayesha', 'Sara']
```

---

# 1️⃣9️⃣ remove()

`remove()` deletes a specific value from the list.

---

## 📘 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

students.remove("Sara")

print(students)
```

Output:

```python
['Zoha Khan', 'Ayesha']
```

---

## 📙 Important Point

`remove()` removes only one value at a time.

It removes the first matching value.

---

# 2️⃣0️⃣ pop()

`pop()` removes a value using index position.

---

## 📘 Example with Index

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

students.pop(1)

print(students)
```

Output:

```python
['Zoha Khan', 'Ayesha']
```

---

## 📙 Explanation

Python removed the value present at:

```python
index 1
```

which was:

```python
Sara
```

---

# 📘 pop() Without Index

If we do not provide any index inside `pop()`:

```python
list.pop()
```

then Python automatically removes the:

```text
Last value
```

from the list.

---

## 📙 Example

```python
students = ["Zoha Khan", "Sara", "Ayesha"]

students.pop()

print(students)
```

Output:

```python
['Zoha Khan', 'Sara']
```

---

## 📗 Explanation

Since no index was provided,

Python automatically removed:

```python
Ayesha
```

because it was the last value.

---

# 2️⃣1️⃣ Difference Between remove() and pop()

| remove() | pop() |
|---|---|
| Removes value by name | Removes value by index |
| Uses actual value | Uses position number |
| Removes first matching value | Removes value from specific index |
| Needs value inside brackets | Index is optional |

---

# 📘 Final List 

| Index | 0 | 1 | 2 |
|---|---|---|---|
| Value | Zoha Khan | Sara | Ayesha |

---