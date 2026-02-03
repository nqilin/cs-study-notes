# Data Structures - List Tuple Dict Set (Python 3.8+)
## Core Basic Knowledge for Python Beginners
This note records the core usage of Python's four built-in basic data structures: **List, Tuple, Dictionary, Set**. They are the foundation of Python data storage and processing, and are often used with loops (`for/while`) and conditional statements (`if/elif/else`) in actual development.

Includes basic definitions, common operations, core characteristics and practical usage scenarios, with runnable code examples and detailed English explanations. All codes are tested and can be executed in Python IDLE/PyCharm/VS Code directly.

> **Key Link**: These data structures are the core of all Python practical development (e.g., file processing, web crawlers, small tools), master their basic usage to realize "data processing + logical control".

---

## 1. Core Concept & Classification
### 1.1 What are Python Data Structures?
Data structures are **ways to store and organize data** in Python, which can improve the efficiency of data access and operation. Python's built-in data structures are easy to use and do not require additional library imports (out-of-the-box).

### 1.2 Key Classification (By Mutability)
The most important classification standard in Python (international mainstream classification), directly determines the usage scenarios:
- **Mutable (can be modified)**: List (`list`), Dictionary (`dict`), Set (`set`) → add/delete/modify elements after creation;
- **Immutable (cannot be modified)**: Tuple (`tuple`) → elements cannot be changed after creation (safe for data storage).

### 1.3 Common Usage Principles
1. Use **List** for ordered, repeatable data storage (most commonly used);
2. Use **Tuple** for ordered, unchangeable data storage (e.g., fixed configuration, coordinate data);
3. Use **Dictionary** for key-value pair data storage (e.g., user information, data mapping);
4. Use **Set** for unordered, non-repeatable data storage (e.g., duplicate removal, intersection/union).

---

## 2. List (`list`) - Most Commonly Used
**Ordered, mutable, repeatable** data structure (the most frequently used in daily development), enclosed in square brackets `[]`, elements are separated by commas.

### 2.1 Basic Definition & Initialization
```python
# Empty list
empty_list = []
# List with different data types (Python's feature: dynamic typing)
mixed_list = [10, "Python", 3.14, True]
# Numeric list (most common)
num_list = [1, 2, 3, 4, 5]
# Nested list (2D list, for table data)
nested_list = [[1,2], [3,4], [5,6]]

print(num_list)  # Output: [1, 2, 3, 4, 5]
print(type(num_list))  # Output: <class 'list'>
```

### 2.2 Common Basic Operations
#### ① Index & Slicing (Same as String, start from 0)
```python
fruits = ["apple", "banana", "orange", "grape"]
# Index: get single element
print(fruits[0])   # First element: apple
print(fruits[-1])  # Last element: grape

# Slicing: [start:end:step] (end is exclusive)
print(fruits[1:3])  # Elements 1-2: ['banana', 'orange']
print(fruits[::2])  # Step 2: ['apple', 'orange']
```

#### ② Add/Delete/Modify Elements (Mutable feature)
```python
nums = [1, 2, 3]
# Modify element (index)
nums[0] = 100
print(nums)  # Output: [100, 2, 3]

# Add element: append() (add to the end, most common)
nums.append(4)
print(nums)  # Output: [100, 2, 3, 4]

# Delete element: remove() (by value) / pop() (by index)
nums.remove(2)
print(nums)  # Output: [100, 3, 4]
nums.pop(0)
print(nums)  # Output: [3, 4]
```

#### ③ Traverse List (Combine with for loop, core usage)
```python
scores = [85, 92, 78, 90]
# Traverse all elements
for score in scores:
    if score >= 90:
        print(f"Excellent: {score}")  # Output: 92, 90

# Traverse with index: enumerate() (get index + element)
for idx, fruit in enumerate(fruits):
    print(f"Index {idx}: {fruit}")
```

---

## 3. Tuple (`tuple`) - Immutable List
**Ordered, immutable, repeatable** data structure, enclosed in parentheses `()`, elements are separated by commas. It is a "safe version" of the list (no accidental modification).

### 3.1 Basic Definition & Initialization
```python
# Empty tuple
empty_tuple = ()
# Numeric tuple
num_tuple = (1, 2, 3, 4, 5)
# Single element tuple (must add comma, key for beginners)
single_tuple = (10,)  # Correct
# single_tuple = (10)  # Wrong: it's an integer, not a tuple

print(num_tuple)  # Output: (1, 2, 3, 4, 5)
print(type(num_tuple))  # Output: <class 'tuple'>
```

### 3.2 Common Basic Operations
> **Key Note**: Tuple is immutable → no add/delete/modify operations, only index/slicing/traversal.
```python
colors = ("red", "green", "blue", "yellow")
# Index & Slicing (same as list/string)
print(colors[1])    # Output: green
print(colors[1:3])  # Output: ('green', 'blue')

# Traverse tuple (same as list)
for color in colors:
    print(f"Color: {color}")

# Nested tuple
nested_tuple = ((1,2), (3,4))
print(nested_tuple[0][1])  # Output: 2
```

### 3.3 Typical Usage Scenario
Use tuple for **fixed, unchangeable data** (international development best practice):
```python
# Fixed coordinate data
point = (100, 200)
# Fixed configuration parameters
config = (8080, "localhost", "utf-8")
# Function return multiple values (automatic conversion to tuple)
def get_info():
    return "GitHub", 18
name, age = get_info()
print(type(get_info()))  # Output: <class 'tuple'>
```

---

## 4. Dictionary (`dict`) - Key-Value Pair
**Unordered (Python 3.7+ ordered), mutable, non-repeatable key** data structure, enclosed in curly brackets `{}`, stored as `key: value` pairs (one key maps to one value). The most important data structure for **data mapping** (e.g., user information).

### 4.1 Core Rules
1. **Key**: unique, immutable (can only be string/int/tuple, not list/set/dict);
2. **Value**: can be any data type (string/int/list/dict, etc.), repeatable;
3. **Access**: get value by key (not index, different from list/tuple).

### 4.2 Basic Definition & Initialization
```python
# Empty dictionary
empty_dict = {}
# User information dictionary (most common scenario)
user = {
    "name": "GitHub Learner",
    "age": 18,
    "is_student": True,
    "scores": [85, 92, 90]  # Value is a list
}

print(user)  # Output: all key-value pairs
print(type(user))  # Output: <class 'dict'>
```

### 4.3 Common Basic Operations
```python
user = {"name": "GitHub Learner", "age": 18, "is_student": True}
# ① Get value by key (2 ways)
print(user["name"])  # Way 1: direct access (error if key not exists)
print(user.get("age"))  # Way 2: get() (safe, return None if key not exists)

# ② Add/Modify key-value pair (same syntax)
user["gender"] = "Male"  # Add new key-value
user["age"] = 19  # Modify value (key exists)
print(user)

# ③ Delete key-value pair: del / pop()
del user["is_student"]
user.pop("gender")
print(user)

# ④ Traverse dictionary (3 common ways)
# Traverse keys (default)
for key in user:
    print(f"Key: {key}")

# Traverse key + value (most common: items())
for key, value in user.items():
    print(f"{key}: {value}")

# Traverse values only: values()
for value in user.values():
    print(f"Value: {value}")
```

---

## 5. Set (`set`) - Unordered Non-Repeatable
**Unordered, mutable, non-repeatable** data structure, enclosed in curly brackets `{}`, no key-value pairs (different from dict). The core usage is **duplicate removal** and **set operations (intersection/union)**.

### 5.1 Basic Definition & Initialization
> **Key Note**: Cannot create empty set with `{}` (it's a dict) → use `set()` for empty set.
```python
# Empty set (must use set())
empty_set = set()
# Numeric set (automatic duplicate removal, key feature)
num_set = {1, 2, 2, 3, 3, 4}
# Convert list to set (duplicate removal)
num_list = [1, 2, 2, 3]
new_set = set(num_list)
print(num_set)  # Output: {1, 2, 3, 4} (no duplicates)
print(type(num_set))  # Output: <class 'set'>
```

### 5.2 Common Basic Operations
```python
s1 = {1, 2, 3, 4}
s2 = {3, 4, 5, 6}
# ① Add/Delete element
s1.add(5)
s1.remove(1)  # Delete (error if element not exists)
print(s1)  # Output: {2, 3, 4, 5}

# ② Core Set Operations (international standard)
print(s1 & s2)  # Intersection (common elements): {3,4,5}
print(s1 | s2)  # Union (all elements, no duplicates): {2,3,4,5,6}
print(s1 - s2)  # Difference (elements in s1 not in s2): {2}

# ③ Duplicate removal for list (practical case)
fruits = ["apple", "banana", "apple", "orange"]
unique_fruits = list(set(fruits))
print(unique_fruits)  # Output: no duplicate fruits
```

---

## 6. Core Comparison of Four Data Structures
A clear summary table for quick review (international technical document style), the most important part for practical use:

| Data Structure | Symbol | Mutability | Order | Duplication | Core Usage |
|----------------|--------|------------|-------|-------------|------------|
| List           | []     | Mutable    | Yes   | Yes         | Ordered data storage, traversal |
| Tuple          | ()     | Immutable  | Yes   | Yes         | Fixed/unchangeable data storage |
| Dictionary     | {}     | Mutable    | Yes*  | No (key)    | Key-value data mapping (user info) |
| Set            | {}     | Mutable    | No    | No          | Duplicate removal, set operations |
*Python 3.7+ dictionary keeps insertion order (de facto standard).

---

## 7. Key Notes & International Coding Habits
1. **Choose the right structure**: Use list for ordered data, dict for key-value mapping, set for duplicate removal – avoid overusing list (the most common beginner error);
2. **Tuple for safety**: Use tuple for fixed data (e.g., configuration, return values) to prevent accidental modification;
3. **Dict key rule**: Key must be immutable (string/int/tuple) – list cannot be a key (causes TypeError);
4. **Set empty creation**: Use `set()` instead of `{}` (avoids confusion with empty dict);
5. **Traversal efficiency**: Use `for ... in ...` for all structures (Python official recommendation), avoid manual index traversal for list;
6. **Meaningful names**: Use plural names for data structures (e.g., `fruits` instead of `fruit` for a fruit list, `users` instead of `user` for a user dict).

---

## 8. Core Summary
1. Python's four core built-in data structures are **List, Tuple, Dictionary, Set** – the foundation of data storage and processing in all practical development;
2. **Mutability** is the most important classification standard: mutable (list/dict/set) for modifiable data, immutable (tuple) for fixed/safe data;
3. **List** is the most commonly used, **Dict** is the most important for data mapping, **Set** is the best for duplicate removal, **Tuple** is for safe fixed data;
4. All data structures are often used with **for loop** and **conditional statements** – this combination is the core of Python practical programming;
5. Master the basic operations and usage scenarios of each structure – the key to writing efficient Python code and developing practical small tools.
