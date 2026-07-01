# 📘 Lecture 09: Dictionaries in Python

Welcome to the Python Summer Camp Class 09!

In this lecture, we will learn about Dictionaries in Python.  
Dictionaries are one of the most powerful and useful data types because they store data in **key-value pairs**.

We use dictionaries to store:

- User information (name, age, email)
- Settings and configurations
- Database records
- JSON data
- Any data that needs a label (key) and a value

---

# Dictionary Concepts

- What is a Dictionary
- Key-Value Pairs
- Dictionary Type
- Ordered vs Unordered
- Dictionary Mutability
- Accessing Dictionary Values
- Updating and Adding Values
- Empty Dictionary
- Nested Dictionaries
- Dictionary Methods
  - keys()
  - values()
  - items()
  - get()
  - update()
  - len()

---

# What is a Dictionary?

A **Dictionary** is a collection of data stored in **key-value pairs**.

In dictionaries:
- Data is stored as pairs
- Each pair has a **key** and a **value**
- Keys are used to access values

### Syntax

```python
dictionary_name = {
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
```

### Example

```python
student = {
    "name": "Zoha Khan",
    "age": 20,
    "city": "Karachi"
}

print(student)
```

Output:

```python
{'name': 'Zoha Khan', 'age': 20, 'city': 'Karachi'}
```

---

# 📗 Key-Value Pairs in Dictionary

Dictionaries store data in **key-value pairs**.

- **Key**: Acts like a label or identifier
- **Value**: The actual data stored

```python
student = {
    "name": "Zoha",     # "name" is key, "Zoha" is value
    "age": 20,          # "age" is key, 20 is value
    "city": "Karachi"   # "city" is key, "Karachi" is value
}
```

---

## Values Can Be Any Data Type

In a dictionary, **values** can be of any type:

- String
- Integer
- Float
- Boolean
- List
- Tuple
- Even another dictionary

### Example

```python
person = {
    "name": "Ali",              # String
    "age": 25,                  # Integer
    "height": 5.8,              # Float
    "is_student": True,         # Boolean
    "hobbies": ["coding", "reading"],  # List
    "coordinates": (24.8, 67.0)        # Tuple
}

print(person)
```

---

## What Can Be Used as Keys?

Keys must be **immutable** (unchangeable) data types.

### ✅ Valid Keys (Immutable)

- String
- Integer
- Float
- Tuple
- Boolean

### ❌ Invalid Keys (Mutable)

- List (because lists can be changed)
- Dictionary (because dictionaries can be changed)

### Why Tuple Can Be Used as Key?

Tuple is **immutable**, which means it cannot be changed after creation.  
That's why tuples can be used as dictionary keys.

### Example

```python
# Valid - Using different immutable types as keys
data = {
    "name": "Zoha",           # String key ✅
    1: "One",                 # Integer key ✅
    (1, 2): "Coordinates",    # Tuple key ✅
    True: "Boolean key"       # Boolean key ✅
}

print(data)
```

### Invalid Example

```python
# Invalid - Using list as key
data = {
    ["name"]: "Zoha"    # ❌ Error: unhashable type: 'list'
}
```

---

# 📙 Dictionary Type

Let's check the type of a dictionary.

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(type(student))
```

Output:

```python
<class 'dict'>
```

The type of dictionary is `dict`.

---

# 📕 Ordered vs Unordered

## Strings, Lists, and Tuples are Ordered

Strings, lists, and tuples have an **index** assigned to each element.  
That's why they are **ordered**.

```python
name = "Python"    # Has index: P=0, y=1, t=2, etc.
numbers = [10, 20, 30]  # Has index: 10=0, 20=1, 30=2
```

---

## Dictionaries are Unordered

Dictionaries do **not have index numbers**.  
That's why dictionaries are **unordered**.

```python
student = {
    "name": "Zoha",
    "age": 20
}

# There is no index like 0, 1, 2
# We access values using keys, not index
```

### Important Note

From **Python 3.7+**, dictionaries maintain **insertion order**.  
But they still don't have numeric indexes like lists.

---

# 📒 Dictionary is Mutable

Dictionaries are **mutable**, which means we can change, add, or delete key-value pairs.

```python
student = {
    "name": "Zoha",
    "age": 20
}

# We can change values
student["age"] = 21

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 21}
```

---

# 📗 Duplicate Keys Are Not Allowed

We **cannot** have the same key twice in a dictionary.

If we use the same key, the **last value** will overwrite the previous one.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "age": 25    # This will overwrite age = 20
}

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 25}
```

As you can see, only the last `age` value is stored.

---

# 📘 Accessing Dictionary Values

To access values from a dictionary, we use **keys** inside **square brackets**.

### Syntax

```python
dictionary_name["key_name"]
```

### Example

```python
student = {
    "name": "Zoha Khan",
    "age": 20,
    "city": "Karachi"
}

print(student["name"])
print(student["age"])
print(student["city"])
```

Output:

```python
Zoha Khan
20
Karachi
```

---

## Error When Key Does Not Exist

If we try to access a key that **does not exist**, Python will give an **error**.

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student["city"])    # ❌ Key 'city' does not exist
```

Output:

```python
KeyError: 'city'
```

This is similar to accessing an invalid index in a list or string.

---

# 📙 Updating and Adding Values

## Updating an Existing Value

To update a value, we assign a new value to an existing key.

```python
student = {
    "name": "Zoha",
    "age": 20
}

# Update age
student["age"] = 21

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 21}
```

---

## Adding a New Key-Value Pair

To add a new key-value pair, we assign a value to a new key.

```python
student = {
    "name": "Zoha",
    "age": 20
}

# Add a new key-value pair
student["city"] = "Karachi"

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 20, 'city': 'Karachi'}
```

---

## Important Point: Same Key Updates, Not Creates New

If we try to add a key that **already exists**, it will **update** the value, not create a new key.

```python
student = {
    "name": "Zoha",
    "age": 20
}

# Trying to add "age" again
student["age"] = 25    # This will update, not create new

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 25}
```

---

# 📕 Empty Dictionary

We can create an **empty dictionary** and add values to it later.

### Creating Empty Dictionary

```python
student = {}

print(student)
print(type(student))
```

Output:

```python
{}
<class 'dict'>
```

---

### Adding Values to Empty Dictionary

```python
student = {}

# Adding values
student["name"] = "Zoha"
student["age"] = 20
student["city"] = "Karachi"

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 20, 'city': 'Karachi'}
```

---

# 📒 Nested Dictionaries

A **nested dictionary** is a dictionary inside another dictionary.

### What is a Nested Dictionary?

When a dictionary contains another dictionary as a value, it's called a nested dictionary.

### Example

```python
students = {
    "student1": {
        "name": "Zoha",
        "age": 20,
        "city": "Karachi"
    },
    "student2": {
        "name": "Ali",
        "age": 22,
        "city": "Lahore"
    }
}

print(students)
```

Output:

```python
{
    'student1': {'name': 'Zoha', 'age': 20, 'city': 'Karachi'}, 
    'student2': {'name': 'Ali', 'age': 22, 'city': 'Lahore'}
}
```

---

## Accessing Nested Dictionary Values

To access values from a nested dictionary, we use **multiple square brackets**.

### Syntax

```python
dictionary["outer_key"]["inner_key"]
```

### Example

```python
students = {
    "student1": {
        "name": "Zoha",
        "age": 20
    },
    "student2": {
        "name": "Ali",
        "age": 22
    }
}

# Accessing nested values
print(students["student1"]["name"])
print(students["student2"]["age"])
```

Output:

```python
Zoha
22
```

---

### Step-by-Step Explanation

```python
students["student1"]              # Returns: {'name': 'Zoha', 'age': 20}
students["student1"]["name"]      # Returns: 'Zoha'
```

First, we access the outer dictionary, then the inner dictionary.

---

# 📗 Dictionary Methods

Python provides built-in methods to work with dictionaries.

---

# 1. keys() Method

The `keys()` method returns all the **keys** of a dictionary.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

print(student.keys())
```

Output:

```python
dict_keys(['name', 'age', 'city'])
```

---

## Converting to List

The `keys()` method returns `dict_keys`, which we can convert to a list using `list()`.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

keys_list = list(student.keys())

print(keys_list)
print(type(keys_list))
```

Output:

```python
['name', 'age', 'city']
<class 'list'>
```

---

# 2. len() Function

The `len()` function returns the **total number of key-value pairs** in a dictionary.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

print(len(student))
```

Output:

```python
3
```

---

# 3. values() Method

The `values()` method returns all the **values** of a dictionary.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

print(student.values())
```

Output:

```python
dict_values(['Zoha', 20, 'Karachi'])
```

---

## Converting to List

The `values()` method returns `dict_values`, which we can convert to a list.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

values_list = list(student.values())

print(values_list)
```

Output:

```python
['Zoha', 20, 'Karachi']
```

---

# 4. items() Method

The `items()` method returns all **key-value pairs** as **tuples**.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

print(student.items())
```

Output:

```python
dict_items([('name', 'Zoha'), ('age', 20), ('city', 'Karachi')])
```

---

## Converting to List

The `items()` method returns `dict_items`, which we can convert to a list.

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

items_list = list(student.items())

print(items_list)
```

Output:

```python
[('name', 'Zoha'), ('age', 20), ('city', 'Karachi')]
```

Each key-value pair is stored as a **tuple** inside the list.

---

# 5. get() Method

The `get()` method returns the **value** of a specified key.

### Syntax

```python
dictionary.get("key_name")
```

### Example

```python
student = {
    "name": "Zoha",
    "age": 20,
    "city": "Karachi"
}

print(student.get("name"))
print(student.get("age"))
```

Output:

```python
Zoha
20
```

---

## Two Ways to Access Values

There are **two ways** to access dictionary values:

### 1. Using Square Brackets

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student["name"])
```

### 2. Using get() Method

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student.get("name"))
```

Both return the same result:

```python
Zoha
```

---

## Difference Between Square Brackets and get()

The main difference appears when we try to access a **key that does not exist**.

### Using Square Brackets

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student["city"])    # ❌ Key does not exist
```

Output:

```python
KeyError: 'city'
```

This gives an **error** and stops the program.

---

### Using get() Method

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student.get("city"))    # ✅ Key does not exist
```

Output:

```python
None
```

The `get()` method returns **None** instead of giving an error.

---

## Which Method is Better?

### Use `get()` When:
- You are not sure if the key exists
- You don't want the program to crash
- You want to provide a default value

### Use Square Brackets `[]` When:
- You are sure the key exists
- You want an error if the key is missing

**Recommendation**: Use `get()` method for safer code.

---

### Providing Default Value with get()

We can provide a **default value** to return if the key does not exist.

```python
student = {
    "name": "Zoha",
    "age": 20
}

print(student.get("city", "Not Found"))
```

Output:

```python
Not Found
```

---

# 6. update() Method

The `update()` method is used to **add** or **update** multiple key-value pairs at once.

### Syntax

```python
dictionary.update({key: value})
```

### Example: Adding New Values

```python
student = {
    "name": "Zoha",
    "age": 20
}

student.update({"city": "Karachi", "course": "Python"})

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 20, 'city': 'Karachi', 'course': 'Python'}
```

---

### Example: Updating Existing Values

```python
student = {
    "name": "Zoha",
    "age": 20
}

student.update({"age": 21})

print(student)
```

Output:

```python
{'name': 'Zoha', 'age': 21}
```

---

## Important Point

If the key passed in `update()` **already exists**, it will **update** the value, not create a new key.

This is because **duplicate keys are not allowed** in dictionaries.

```python
student = {
    "name": "Zoha",
    "age": 20
}

student.update({"name": "Ali", "age": 25})    # Updates existing keys

print(student)
```

Output:

```python
{'name': 'Ali', 'age': 25}
```

---

# 📗 Summary Table

| Method | Description | Returns |
|--------|-------------|---------|
| `keys()` | Returns all keys | dict_keys (can convert to list) |
| `values()` | Returns all values | dict_values (can convert to list) |
| `items()` | Returns key-value pairs as tuples | dict_items (can convert to list) |
| `get()` | Returns value for a key (safe access) | Value or None |
| `update()` | Adds or updates multiple key-value pairs | None (modifies original) |
| `len()` | Returns number of key-value pairs | Integer |

---

# 📘 Key Points to Remember

- Dictionaries store data in **key-value pairs**
- Keys must be **immutable** (string, int, tuple, etc.)
- Values can be **any data type**
- Dictionaries are **mutable**
- **No duplicate keys** allowed
- Dictionaries are **unordered** (no index)
- Use `[]` to access values (can give error)
- Use `get()` for safe access (returns None if key missing)
- Use `update()` to add/update multiple items
- Nested dictionaries can store complex data

---

# 📗 Complete Example

```python
# Creating a dictionary
person = {
    "name": "Zoha Khan",
    "age": 20,
    "city": "Karachi",
    "hobbies": ["coding", "reading"],
    "is_student": True
}

# Accessing values
print(person["name"])
print(person.get("city"))

# Adding new key-value pair
person["email"] = "zoha@example.com"

# Updating existing value
person["age"] = 21

# Dictionary methods
print(person.keys())
print(person.values())
print(person.items())
print(len(person))

# Nested dictionary example
students = {
    "student1": {"name": "Zoha", "age": 20},
    "student2": {"name": "Ali", "age": 22}
}

print(students["student1"]["name"])
```

---

Happy Learning! 🎉
