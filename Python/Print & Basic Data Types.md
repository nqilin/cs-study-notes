# Print Function & Basic Data Types (Python 3.8+)
## Core Basic Knowledge for Python Beginners
This note records the core usage of Python's print function and basic built-in data types, with **runnable code examples** and detailed explanations. All codes are tested and can be directly executed in Python IDLE/PyCharm/VS Code.

---

## 1. The Print Function
### 1.1 Basic Usage
The `print()` function is the most basic output function in Python, used to display text/numbers/variables on the console.
**Syntax**: `print(object(s), sep=separator, end=end, file=file, flush=flush)`
- **Default**: Separate multiple objects with spaces (`sep=' '`), end with a newline (`end='\n'`)

### 1.2 Common Usage Examples
```python
# Example 1: Print a single string/number
print("Hello Python")  # Output: Hello Python
print(123 + 456)      # Output: 579

# Example 2: Print multiple objects (separated by space by default)
print("Name:", "Alex", "Age:", 19)  # Output: Name: Alex Age: 19

# Example 3: Custom separator (sep) and end character (end)
print("Python", "Java", "C++", sep=" | ")  # Output: Python | Java | C++
print("First line", end=" ")
print("Second line")  # Output: First line Second line

# Example 4: Print with variables
name = "GitHub Learner"
age = 18
print(f"Hello, my name is {name}, I am {age} years old.")  # F-string (Python 3.6+)
```

**Key Note**: F-string (`f""`) is the most concise and commonly used way to format strings in Python (recommended for daily development).


## 2. Basic Built-in Data Types
Python is a dynamically typed language (no need to declare variable types), the core basic data types are divided into 4 categories **Number, String, Boolean, NoneType**, all are built-in and can be used directly.
### 2.1 Number (Numeric Type)
Include `int` (integer), `float` (floating point), no `long` in Python 3.
```python
运行
# Int (integer, positive/negative/zero)
a = 100
b = -50
print(type(a))  # Output: <class 'int'>

# Float (floating point, with decimal point)
c = 3.14
d = 2.0
print(type(c))  # Output: <class 'float'>

# Basic arithmetic operations
print(10 + 3)   # Addition: 13
print(10 - 3)   # Subtraction:7
print(10 * 3)   # Multiplication:30
print(10 / 3)   # Division:3.333...
print(10 // 3)  # Integer division:3
print(10 % 3)   # Modulus (remainder):1
print(10 **3)  # Exponent:1000
```

### 2.2 String (str)
A sequence of characters enclosed in single quotes (`' '`), double quotes (`" "`) or triple quotes (`''' '''/""" """`).
```python
# Basic string definition
s1 = "Hello GitHub"
s2 = 'Python Study'
s3 = """Multi-line
String"""  # Support multi-line text

# String indexing (start from 0)
print(s1[0])   # Output: H
print(s1[-1])  # Output: b (last character)

# String slicing: [start:end:step] (end is exclusive)
print(s1[0:5]) # Output: Hello

# Basic string operation
print(s1 + " !")  # Concatenation: Hello GitHub !
print(s1 * 2)     # Repeat: Hello GitHubHello GitHub
```

### 2.3 Boolean (bool)
Only two values: `True` (1) and `False` (0), used for conditional judgment (if/while statements).
```python
# Basic boolean definition
is_student = True
is_adult = False
print(type(is_student))  # Output: <class 'bool'>

# Boolean from comparison operations
print(10 > 3)   # True
print(10 == 3)  # False
print(10 != 3)  # True
```

### 2.4 NoneType (None)
Represents an empty value (not 0/''/[]), used to initialize variables or return empty values.
```python
# None definition
x = None
print(x)        # Output: None
print(type(x))  # Output: <class 'NoneType'>

# Key Note: None is not equal to any value
print(None == 0)  # False
print(None == "") # False
```

### 2.5 Check Data Type: type() & isinstance()
`type(object)`: Return the exact type of the object;
`isinstance(object, class)`: Check if the object is an instance of the class (more recommended for type judgment).
```python
num = 100
print(type(num))          # <class 'int'>
print(isinstance(num, int))  # True

s = "Python"
print(isinstance(s, str)) # True
```

## 3. Core Summary
The `print()` function is the basic output tool, **F-string** is the best practice for formatted output;
Python basic data types: `Number` (int/float)、`String` (str)、`Boolean` (bool)、`NoneType` (None);
Python is dynamically typed – variable type is determined when assigning a value, no need to declare;
Use `type()` to check the exact type, `isinstance()` for type judgment in development;
All basic data types support direct assignment and simple operations, which is the foundation of Python programming.
