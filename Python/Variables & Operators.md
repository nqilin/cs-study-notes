# Variables & Operators (Python 3.8+)
## Core Basic Knowledge for Python Beginners
This note records the core usage of Python variables (definition, naming, assignment) and common operators (arithmetic, comparison, logical, assignment), with runnable code examples and detailed English explanations. All codes are tested and can be executed in Python IDLE/PyCharm/VS Code directly.

---

## 1. Python Variables
A variable is a **named storage location** used to store data values in a program. Python variables are dynamically typed – the data type is determined automatically when a value is assigned, no need for explicit declaration.

### 1.1 Variable Naming Rules (MUST FOLLOW)
Python has strict naming rules for variables (violating them will cause syntax errors), which are the same as international programming standards:
1. Can only consist of **letters (a-z/A-Z)**, **numbers (0-9)** and **underscore (_)**;
2. **Cannot start with a number** (e.g., `1var` is invalid, `var1` is valid);
3. **Case-sensitive** (e.g., `Name` and `name` are two different variables);
4. Cannot use **Python reserved keywords** (e.g., `if`, `else`, `for`, `while`, `print`, `type`);
5. Use **snake_case** for multi-word naming (Python official recommendation) – lowercase letters + underscore separation (e.g., `student_name`, `age_2024`).

**Key Note**: Use meaningful variable names (not random letters like `a/b/c`), which improves code readability (critical for team development and job interviews).

### 1.2 Variable Assignment
The **equal sign (=)** is the assignment operator in Python – it assigns the value on the right to the variable on the left. Support multiple assignment methods for different scenarios.

```python
# Example 1: Basic single assignment (most commonly used)
student_name = "GitHub Learner"
student_age = 18
is_coder = True
print(student_name, student_age)  # Output: GitHub Learner 18

# Example 2: Multiple variables assign the same value
x = y = z = 100
print(x, y, z)  # Output: 100 100 100

# Example 3: Multiple variables assign different values (one line)
a, b, c = 1, 2.5, "Python"
print(a, b, c)  # Output: 1 2.5 Python

# Example 4: Variable type change (dynamic typing)
num = 10  # int type
num = 3.14  # float type (reassign, type changes automatically)
num = "Python"  # str type
print(type(num))  # Output: <class 'str'>
```

### 1.3 Delete Variable (del keyword)
Use the `del` keyword to delete a variable and release the storage space (rarely used in basic development, but useful for memory optimization).
```python
score = 95
print(score)  # Output: 95
del score
# print(score)  # Error: NameError (variable is deleted)
```

---

## 2. Common Python Operators
Operators are symbols used to perform operations on variables and values. Python divides common operators into 4 core categories (sorted by usage frequency), all with standard international usage.

### 2.1 Arithmetic Operators
Used for basic mathematical calculations, the same as standard mathematical symbols (supports `+ - * / // % **`).
```python
a = 10
b = 3

# Basic arithmetic
print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division (float result): 3.333...
print(a // b)  # Integer division (discard decimal): 3
print(a % b)   # Modulus (remainder): 1
print(a ** b)  # Exponentiation (a^b): 1000
```

### 2.2 Comparison Operators
Used to compare two values, return a **Boolean value (True/False)** (core for conditional judgment: if/while).
**Operators**: `== != > < >= <=`
```python
x = 10
y = 15

print(x == y)  # Equal: False
print(x != y)  # Not equal: True
print(x > y)   # Greater than: False
print(x < y)   # Less than: True
print(x >= y)  # Greater or equal: False
print(x <= y)  # Less or equal: True
```

### 2.3 Logical Operators
Used to combine multiple Boolean conditions, return a single Boolean value. **3 core operators**: `and` (and), `or` (or), `not` (not) – international standard naming.
```python
# Define basic conditions
age = 18
is_student = True

# and: All conditions are True → return True
print(age >= 18 and is_student)  # True and True → True

# or: One condition is True → return True
print(age < 18 or is_student)   # False or True → True

# not: Reverse the Boolean value
print(not is_student)  # not True → False
print(not (age > 20))  # not False → True
```

### 2.4 Assignment Operators
Used to assign values to variables, the basic `=` plus arithmetic operators (simplify code, official recommendation).
**Common**: `= += -= *= /= %= **= //=`
```python
n = 10

n += 5  # Equivalent to n = n + 5 → 15
print(n)

n -= 3  # Equivalent to n = n - 3 → 12
print(n)

n *= 2  # Equivalent to n = n * 2 → 24
print(n)

n /= 4  # Equivalent to n = n / 4 → 6.0
print(n)
```

---

## 3. Core Summary
1. Python variables are **dynamically typed** – no type declaration, type is determined by the assigned value and can be changed by reassignment;
2. Follow **snake_case** naming rule and avoid reserved keywords – meaningful variable names improve code readability (critical for job/cooperation);
3. Python supports multiple assignment methods (single/multiple/same value) to adapt to different development scenarios;
4. The 4 core operator categories are **Arithmetic, Comparison, Logical, Assignment** – master their usage for basic conditional judgment and calculation;
5. Comparison operators return Boolean values, Logical operators combine conditions – both are the foundation of Python control flow (if/while, to be learned later);
6. Assignment operators (`+= -=` etc.) simplify code and are the standard writing method in international Python development.
