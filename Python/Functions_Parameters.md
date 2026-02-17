# Functions & Parameters

## 1. What is a Function?
A function is a reusable block of code that performs a specific task. It helps avoid repetition and makes code more modular and readable.

```python
# Example: a simple function
def greet():
    print("Hello, welcome to CS-Study-Notes!")

greet()  # Output: Hello, welcome to CS-Study-Notes!
```

---

## 2. Defining a Function
Use the `def` keyword to define a function, followed by the function name, parentheses `()`, and a colon `:`. The code block inside the function is indented.

```python
def function_name(parameters):
    # function body
    return result
```

---

## 3. Parameters & Arguments
- **Parameter**: A variable listed inside the parentheses in the function definition.
- **Argument**: The actual value passed to the function when it is called.

### 3.1 Positional Arguments
Arguments are assigned to parameters based on their position.

```python
def add(a, b):
    return a + b

result = add(3, 5)  # a=3, b=5
print(result)       # Output: 8
```

### 3.2 Keyword Arguments
Arguments are passed by explicitly naming the parameter, regardless of order.

```python
def describe_pet(name, animal_type):
    print(f"I have a {animal_type} named {name}.")

describe_pet(animal_type="dog", name="Buddy")
# Output: I have a dog named Buddy.
```

### 3.3 Default Parameters
A parameter can have a default value. If no argument is provided, the default is used.

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()              # Output: Hello, Guest!
greet("Alice")       # Output: Hello, Alice!
```

### 3.4 Variable-Length Arguments
- `*args`: Allows a function to accept an arbitrary number of positional arguments (as a tuple).
- `**kwargs`: Allows a function to accept an arbitrary number of keyword arguments (as a dictionary).

```python
# *args example
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3, 4))  # Output: 10

# **kwargs example
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Bob", age=25, city="New York")
# Output:
# name: Bob
# age: 25
# city: New York
```

---

## 4. Return Values
The `return` statement exits a function and sends a value back to the caller. A function can return any data type, including lists, dictionaries, or even other functions.

```python
def square(x):
    return x * x

result = square(4)
print(result)  # Output: 16

# Returning multiple values (as a tuple)
def get_coordinates():
    return 10, 20

x, y = get_coordinates()
print(x, y)  # Output: 10 20
```

---

## 5. Scope of Variables
- **Local Variables**: Defined inside a function and only accessible within that function.
- **Global Variables**: Defined outside all functions and accessible throughout the script.

```python
global_var = "I'm global"

def my_function():
    local_var = "I'm local"
    print(global_var)  # Accessible
    print(local_var)   # Accessible

my_function()
print(global_var)      # Accessible
# print(local_var)    # Error: NameError (not accessible outside function)
```

---

## 6. Lambda Functions (Anonymous Functions)
A lambda function is a small, anonymous function defined with the `lambda` keyword. It can take any number of arguments but can only have one expression.

```python
# Syntax: lambda arguments: expression
double = lambda x: x * 2
print(double(5))  # Output: 10

# Use with map()
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # Output: [1, 4, 9, 16]
