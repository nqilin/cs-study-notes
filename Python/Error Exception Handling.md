# Error & Exception Handling

## 1. What is an Exception?
An exception is an error that occurs during the execution of a program. When an exception is not handled, the program terminates abruptly. Python provides a way to catch and handle exceptions so that the program can continue running.

---

## 2. Common Exceptions
Here are some common built-in exceptions in Python:

| Exception          | Description                                  |
|--------------------|----------------------------------------------|
| `SyntaxError`      | Invalid Python syntax                        |
| `NameError`        | Accessing a variable that is not defined     |
| `TypeError`        | Operation on an incompatible type            |
| `IndexError`       | Accessing a sequence with an invalid index   |
| `KeyError`         | Accessing a dictionary with an invalid key   |
| `ValueError`       | Function receives an argument of the right type but wrong value |
| `ZeroDivisionError`| Division by zero                             |
| `FileNotFoundError`| Trying to open a file that does not exist    |

---

## 3. The `try-except` Block
Use a `try-except` block to catch and handle exceptions.

```python
try:
    # Code that might raise an exception
    x = 1 / 0
except ZeroDivisionError:
    # Code to run if the exception occurs
    print("Error: Cannot divide by zero!")
```

### 3.1 Handling Multiple Exceptions
You can handle multiple exceptions in a single `except` block or use separate `except` blocks.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Error: Please enter a valid integer.")
except ZeroDivisionError:
    print("Error: Cannot divide by zero.")
```

### 3.2 Catching All Exceptions
Use a bare `except` clause to catch all exceptions, but it is generally not recommended as it can hide unexpected errors.

```python
try:
    # risky code
except:
    print("An error occurred.")
```

---

## 4. The `else` Clause
The `else` clause runs if the code in the `try` block does not raise an exception.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Error: Please enter a valid integer.")
except ZeroDivisionError:
    print("Error: Cannot divide by zero.")
else:
    print(f"Result: {result}")
```

---

## 5. The `finally` Clause
The `finally` clause runs regardless of whether an exception occurred or not. It is often used for cleanup operations, like closing a file.

```python
try:
    file = open("example.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("Error: File not found.")
finally:
    if 'file' in locals():
        file.close()
        print("File closed.")
```

---

## 6. Raising Exceptions
Use the `raise` statement to manually trigger an exception.

```python
def check_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative.")
    print(f"Age is {age}")

try:
    check_age(-5)
except ValueError as e:
    print(f"Error: {e}")  # Output: Error: Age cannot be negative.
```

---

## 7. Custom Exceptions
You can define your own exceptions by creating a class that inherits from the built-in `Exception` class.

```python
class InvalidAgeError(Exception):
    pass

def check_age(age):
    if age < 0:
        raise InvalidAgeError("Age cannot be negative.")

try:
    check_age(-5)
except InvalidAgeError as e:
    print(f"Custom Error: {e}")  # Output: Custom Error: Age cannot be negative.
