# C++ Basic Syntax & Variables

C++ is a statically-typed, compiled programming language that extends the C language with object-oriented programming (OOP) features. This note covers fundamental syntax rules, variable declaration, data types, and input/output operations for beginners.

---

## 1. Core Program Structure
A minimal C++ program consists of three essential components:
- Header files (for accessing standard libraries)
- The `main()` function (mandatory entry point of all C++ programs)
- Input/output operations (via the `iostream` library)

### Example: Hello World (Basic Template)
```cpp
// Include the standard input/output stream library
#include <iostream>

// Use the standard namespace to simplify code (avoids "std::" prefix)
using namespace std;

// Main function: program starts here
int main() {
    // Output text to the console (cout = character output)
    cout << "Hello, C++ World!" << endl;
    
    // Return 0 to indicate successful program execution
    return 0;
}
```

### How to Compile & Run
Save the code as `hello.cpp`, then use these commands in terminal/command prompt:
```bash
# Compile (g++ is the C++ compiler)
g++ hello.cpp -o hello

# Run the executable
./hello          # Linux/macOS
hello.exe        # Windows
```

---

## 2. Key Syntax Rules
### 2.1 Comments (For Documentation)
Comments are ignored by the compiler and used to explain code:
```cpp
// Single-line comment (starts with //)

/*
Multi-line comment
Can span multiple lines
Useful for longer explanations
*/
```

### 2.2 Statements & Semicolons
Every individual statement must end with a semicolon (`;`) — this is a critical rule in C++:
```cpp
int age = 20;          // Valid (ends with ;)
cout << "Age: " << age // Invalid (missing semicolon → compile error)
```

### 2.3 Code Blocks
Related code is grouped into blocks using curly braces `{}` (used for functions, loops, conditionals):
```cpp
// Block for main function
int main() {
    // Block for if statement
    if (age > 18) {
        cout << "Adult" << endl;
        cout << "Eligible to vote" << endl;
    }
    return 0;
}
```

---

## 3. Variables
### 3.1 Declaration & Initialization
C++ is statically-typed — variables must be declared with a **data type** before use:

| Syntax Style               | Description                  | Example                          |
|----------------------------|------------------------------|----------------------------------|
| Declaration only           | Define type + name (no value)| `int score;`                     |
| Direct initialization      | Declare + assign value       | `double pi = 3.14159;`           |
| Constructor initialization | Alternative C++ style        | `char grade('A');`               |
| Type inference (C++11+)    | Auto-detect type (with `auto`)| `auto num = 100;` (infers `int`) |

### 3.2 Naming Conventions (Best Practices)
- Must start with a letter (`a-z`, `A-Z`) or underscore (`_`)
- Can contain letters, digits (`0-9`), and underscores
- Case-sensitive (`age` ≠ `Age` ≠ `AGE`)
- Cannot use C++ keywords (e.g., `int`, `if`, `for`, `while`, `class`)

### 3.3 Variable Scope
Scope determines where a variable is accessible in the program:
```cpp
// Global variable (accessible everywhere in the program)
int global_number = 100;

int main() {
    // Local variable (only accessible inside main())
    int local_number = 50;
    
    cout << global_number << endl; // Valid (output: 100)
    cout << local_number << endl;  // Valid (output: 50)
    return 0;
}

// cout << local_number << endl; // Error: local_number is out of scope
```

---

## 4. Basic Data Types
C++ provides built-in fundamental data types (sizes may vary slightly by operating system):

| Type       | Description                  | Typical Size (Bytes) | Example Usage                  |
|------------|------------------------------|----------------------|--------------------------------|
| `int`      | Integer (whole numbers)      | 4                    | `int count = 5;`               |
| `float`    | Single-precision float       | 4                    | `float height = 1.75f;`        |
| `double`   | Double-precision float       | 8                    | `double weight = 72.5;`        |
| `char`     | Single character             | 1                    | `char initial = 'J';`          |
| `bool`     | Boolean (true/false)         | 1                    | `bool is_student = true;`      |
| `short`    | Short integer                | 2                    | `short year = 2024;`           |
| `long`     | Long integer                 | 8                    | `long population = 8000000000L;`|

### 4.1 Type Modifiers
Modify the behavior of basic data types:
- `unsigned`: Restricts to non-negative values (0 and above)
- `const`: Makes a variable read-only (immutable)

```cpp
// Unsigned int (range: 0 to 4294967295)
unsigned int positive_score = 95;

// Const variable (cannot be modified after initialization)
const double PI = 3.14159;
// PI = 3.14; // Error: assignment of read-only variable 'PI'
```

---

## 5. Input & Output (I/O)
### 5.1 Output with `cout`
Use `cout` (character output) to print to the console:
```cpp
int x = 10, y = 20;
// Chain multiple values (<< = insertion operator)
cout << "x = " << x << ", y = " << y << endl;
// Output: x = 10, y = 20
```

### 5.2 Input with `cin`
Use `cin` (character input) to read user input:
```cpp
string name;
int age;

cout << "Enter your name: ";
cin >> name; // Read string input
cout << "Enter your age: ";
cin >> age;  // Read integer input

cout << "Hello " << name << ", you are " << age << " years old." << endl;
```

---

## 6. Type Conversion
### 6.1 Implicit Conversion (Automatic)
Compiler automatically converts compatible types (safe for "widening" conversions):
```cpp
int a = 5;
double b = a; // int → double (5 → 5.0)
cout << b << endl; // Output: 5
```

### 6.2 Explicit Conversion (Casting)
Manually convert types (use C++-style casting for safety):
```cpp
double c = 3.14;
// C-style cast (simple but less safe)
int d = (int)c; // 3.14 → 3
// C++-style cast (recommended)
int e = static_cast<int>(c); // 3.14 → 3

cout << d << endl; // Output: 3
cout << e << endl; // Output: 3
