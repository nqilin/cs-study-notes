# Control Flow - Loops (for & while) (Python 3.8+)
## Core Basic Knowledge for Python Beginners
This note records the core usage of Python two core loop statements (`for` & `while`), the foundation of program **batch repeated code execution**. Includes basic syntax, common usage scenarios, `break/continue` keywords, loop nesting and practical cases, with runnable code examples and detailed English explanations. All codes are tested and can be executed in Python IDLE/PyCharm/VS Code directly.

> **Key Link**: Loops are often used with conditional statements (`if/elif/else`) to implement complex logical programming – the most basic and commonly used combination in Python development.

---

## 1. Python Loop Statements: Basic Concept
Loop statements are used to **execute the same code block repeatedly** according to specific conditions, which can greatly reduce redundant code and improve development efficiency.

Python has two core loop types (sorted by actual development usage frequency):
1. **for loop**: More commonly used – for traversing/iterating over a sequence (string/list/tuple, etc.) or a fixed number of times (with `range()`);
2. **while loop**: For looping according to a Boolean condition – run until the condition becomes `False`.

**Core Syntax Rules (Same as Conditional Statements)**:
- Must add a colon (`:`) after the loop condition/statement;
- The loop code block must be **indented (4 spaces)** (Python official international standard, no mixed tabs/spaces);
- Indentation level determines the code block scope (critical for loop nesting).

---

## 2. The `for` Loop (Most Commonly Used)
The `for` loop is designed for **iterable object traversal** (the most common scenario in daily development). The `range()` function is often used to generate a numeric sequence for fixed-number loop execution (international mainstream usage).

### 2.1 Basic Syntax
```
for variable in iterable_object/sequence:
    # Indented code block (4 spaces)
    repeated_executed_code
```
- `variable`: Temporary variable (custom name, meaningful is better);
- `in`: Python keyword for traversal (fixed);
- `iterable_object`: Iterable object (string, list, `range()`, etc.).

### 2.2 Common Usage Scenarios
#### Scenario 1: Traverse a String
```python
# Traverse each character in the string
message = "Python"
for char in message:
    print(char)  # Output: P → y → t → h → o → n (one per line)
```

#### Scenario 2: Fixed-number Loop with `range()` Function
**`range()` Syntax**: `range(start, end, step)` (end is exclusive, step default=1)
- `range(n)`: 0 to n-1;
- `range(a, b)`: a to b-1;
- `range(a, b, s)`: a to b-1, step s.
```python
# Example 1: Loop 5 times (0-4)
for i in range(5):
    print(f"Loop times: {i+1}")  # Output: 1-5 (one per line)

# Example 2: Loop from 3 to 7 (3-6)
for num in range(3, 7):
    print(num)  # Output: 3 → 4 → 5 → 6

# Example 3: Loop with step 2 (1,3,5,7,9)
for n in range(1, 10, 2):
    print(n)
```

#### Scenario 3: Traverse a Simple Numeric List
```python
# Traverse each element in the list (Python basic data structure, to be learned later)
scores = [85, 92, 78, 90]
for score in scores:
    if score >= 90:
        print(f"Excellent score: {score}")  # Output: 92 → 90
```

---

## 3. The `while` Loop
The `while` loop runs the code block **as long as the Boolean condition is `True`**, and stops when the condition becomes `False`. Suitable for scenarios where the **loop times are uncertain** (unlike for loop with fixed times).

### 3.1 Basic Syntax
```
while boolean_condition:
    # Indented code block (4 spaces)
    repeated_executed_code
    # Must have a statement to change the condition (avoid infinite loop!)
```

### 3.2 Common Usage Scenarios
#### Scenario 1: Basic Condition Loop
```python
# Loop until count >= 5
count = 1
while count <= 5:
    print(f"Count: {count}")
    count += 1  # Critical: count +1, change the condition (avoid infinite loop)
# Output: 1 → 2 → 3 → 4 → 5
```

#### Scenario 2: Loop with Conditional Jump (`break/continue`)
- `break`: **Terminate the entire loop** immediately (skip all subsequent iterations);
- `continue`: **Skip the current iteration** only (continue the next iteration);
*Two keywords are international standard, used in all programming languages (C++/Java/Python).*
```python
# Example 1: Use break to terminate the loop when count == 3
num = 1
while num <= 5:
    if num == 3:
        break
    print(num)
    num += 1
# Output: 1 → 2 (loop stops at 3)

# Example 2: Use continue to skip num == 3
num = 0
while num < 5:
    num += 1
    if num == 3:
        continue
    print(num)
# Output: 1 → 2 → 4 → 5 (3 is skipped)
```

### 3.3 Critical Note: Avoid Infinite Loop
**Infinite Loop**: The loop condition is always `True` (the code runs forever, causes program crash).
**How to Avoid** (international development best practice):
1. Always set a **counter variable** (e.g., `count/num`);
2. Update the counter in the loop (e.g., `count +=1`/`count -=1`);
3. Never write a fixed `True` condition in basic development (e.g., `while True:` unless necessary).

---

## 4. Loop Nesting
Put a loop **inside another loop's code block** (indentation determines the nesting level) – used for **two-dimensional traversal** (e.g., table data, multiplication table). Follow international coding habits: **keep nesting level ≤ 2 layers** (ensure code readability).

### 4.1 Basic Nested Syntax (for-in-for)
```python
# Example: Print a 3x3 star matrix (simple 2-layer for loop)
for i in range(3):  # Outer loop: control rows
    for j in range(3):  # Inner loop: control columns
        print("*", end=" ")  # No newline, print in the same line
    print()  # Newline after each row
# Output:
# * * *
# * * *
# * * *
```

### 4.2 Practical Case: 9x9 Multiplication Table (Simplified Version)
```python
# Print a simple 5x5 multiplication table (easy to understand, no complex logic)
for i in range(1, 6):
    for j in range(1, i+1):
        print(f"{j}×{i}={i*j}", end="\t")  # \t: tab, align the output
    print()  # Newline after each row
```

---

## 5. Key Notes & International Coding Habits
1. **Indentation is mandatory**: 4 spaces per indentation (Python official standard), no mixed tabs and spaces (causes format errors in international team development);
2. **Avoid infinite loops**: Always update the condition variable in `while` loop (the most common beginner error);
3. **Choose the right loop**: Use `for` loop for **fixed times/traversal** (80% of scenarios), `while` loop for **uncertain loop times**;
4. **Minimize nesting**: Nesting >2 layers reduces code readability (unpopular in international development);
5. **Meaningful variable names**: Avoid single letters like `i/j` in complex loops (e.g., `row/col` for matrix, `score` for score traversal);
6. **Combine with condition statements**: Loops + `if/elif/else` are the core of practical programming (e.g., filter data while traversing).

---

## 6. Core Summary
1. Python has two core loops: `for` (fixed times/traversal, **most commonly used**) and `while` (uncertain loop times based on Boolean condition);
2. **Colon (`:`) and 4-space indentation** are mandatory core syntax (Python international standard);
3. `range(start, end, step)` is the key to using `for` loop for fixed-number execution (end index is exclusive);
4. `break` terminates the **entire loop**, `continue` skips the **current iteration** (both are international standard keywords);
5. Loop nesting is for two-dimensional traversal, keep nesting level **≤2 layers** to ensure readability;
6. Loops + conditional statements (`if/elif/else`) form the **basic logical framework of Python programming** – the foundation of all practical tool development and algorithm problem-solving;
7. Always follow international coding habits (meaningful variable names, minimal nesting, standard indentation) for team cooperation and job hunting.
