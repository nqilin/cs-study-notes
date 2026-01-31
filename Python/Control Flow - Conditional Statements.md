# Control Flow - Conditional Statements (Python 3.8+)
## Core Basic Knowledge for Python Beginners
This note records the core usage of Python conditional statements (`if/elif/else`), the foundation of program **logical judgment and branch control**. Includes basic syntax, multi-condition judgment, nested statements and practical cases, with runnable code examples and detailed English explanations. All codes are tested and can be executed in Python IDLE/PyCharm/VS Code directly.

---

## 1. What are Conditional Statements?
Conditional statements execute **different code blocks** according to the result of **Boolean condition judgment (True/False)**. They are the most basic control flow statements in Python, and are widely used in all programming scenarios (tool development, algorithm problems, etc.).

**Core Logic**: Judge first, then execute → If the condition is True, run the corresponding code; if False, skip or run the alternative code.
**Key Symbols**: Colon (`:`) after the condition → Indentation (`4 spaces`/`1 tab`) for the code block (Python's core syntax, must follow).

> **International Coding Standard**: Use 4 spaces for indentation (Python official recommendation), consistent with the coding habits of foreign developers.

---

## 2. Basic Syntax of Conditional Statements
Python has three core conditional statement forms, sorted by usage frequency: basic `if`, `if-else`, and `if-elif-else` (for multi-condition judgment).

### 2.1 Basic `if` Statement (Single Condition)
Run the code block **only when the condition is True**; do nothing if False.
**Syntax**:
```
if boolean_condition:
    # Indented code block (4 spaces)
    execute_code
```
```python
# Example: Judge if the age is an adult
age = 19
if age >= 18:
    print("You are an adult.")  # Output: You are an adult.

# Example: Condition is False (no output)
score = 59
if score >= 60:
    print("Pass the exam.")
```

### 2.2 `if-else` Statement (Two Conditions)
**Dual branch control**: Run the `if` code block when the condition is True, and the `else` code block when False (one of the two must run).
**Syntax**:
```
if boolean_condition:
    execute_code1
else:
    execute_code2
```
```python
# Example: Exam pass/fail judgment
score = 75
if score >= 60:
    print("Pass the exam. Congratulations!")  # Output: Pass the exam. Congratulations!
else:
    print("Fail the exam. Please study harder.")

# Example: Number positive/negative judgment
num = -8
if num > 0:
    print("This is a positive number.")
else:
    print("This is a non-positive number.")  # Output: This is a non-positive number.
```

### 2.3 `if-elif-else` Statement (Multiple Conditions)
**Multi-branch control**: For 3+ conditions, judge in order from top to bottom (only the first True condition's code block runs). Use `elif` (else if) for intermediate conditions, `else` for the final default condition.
**Syntax**:
```
if condition1:
    execute_code1
elif condition2:
    execute_code2
elif condition3:
    execute_code3
else:
    execute_default_code
```
```python
# Example: Grade evaluation (practical case, international common grading standard)
score = 88
if score >= 90:
    print("Grade: A (Excellent)")
elif score >= 80:
    print("Grade: B (Good)")  # Output: Grade: B (Good)
elif score >= 70:
    print("Grade: C (Average)")
elif score >= 60:
    print("Grade: D (Pass)")
else:
    print("Grade: F (Fail)")

# Example: Judge the size relationship of three numbers
a, b, c = 15, 20, 10
if a > b and a > c:
    print(f"{a} is the largest number.")
elif b > a and b > c:
    print(f"{b} is the largest number.")  # Output: 20 is the largest number.
else:
    print(f"{c} is the largest number.")
```

---

## 3. Nested Conditional Statements
Put a conditional statement **inside another conditional statement's code block** (indentation determines the nesting level). Used for **complex multi-layer judgment**, keep the nesting level as low as possible (1-2 layers) to ensure code readability (international coding best practice).
**Syntax**: Indent the inner `if/elif/else` 4 more spaces than the outer one.
```python
# Example: Adult judgment + student identity judgment (2-layer nesting)
age = 20
is_student = True

if age >= 18:
    print("You are an adult.")
    # Inner nested if statement (4 more spaces indentation)
    if is_student:
        print("And you are a college student.")  # Output both lines
    else:
        print("And you are a social person.")
else:
    print("You are a minor.")

# Example: Nested elif (simple complex judgment)
num = 0
if num >= 0:
    if num == 0:
        print("The number is zero.")  # Output
    else:
        print("The number is positive.")
else:
    print("The number is negative.")
```

---

## 4. Key Notes & International Coding Habits
1. **Colon & Indentation are mandatory**: Missing colon (`:`) or incorrect indentation will cause **SyntaxError** (the most common error for beginners);
2. **One condition, one indentation level**: Use 4 spaces for each indentation (no tabs mixed with spaces, avoid format errors);
3. **Simplify conditions**: Use logical operators (`and/or/not`) to combine multiple conditions, avoid overly long single condition expressions;
4. **Minimize nesting**: Nesting more than 3 layers will reduce code readability (unpopular in international team development);
5. **Meaningful condition comments**: Add comments for complex conditions to explain the judgment logic (help others understand your code).

---

## 5. Core Summary
1. Python conditional statements (`if/elif/else`) implement **branch control** based on Boolean condition judgment (True/False);
2. **Colon (`:`) and 4-space indentation** are core syntax, mandatory (Python's unique feature, international standard);
3. Use `if` for single condition, `if-else` for dual branch, `if-elif-else` for **multi-condition judgment** (most commonly used);
4. Nested conditional statements are for complex judgment, keep nesting level **1-2 layers** to ensure readability;
5. Conditional statements are the foundation of Python logical programming, and are the prerequisite for learning loops (`for/while`) and developing practical tools.
