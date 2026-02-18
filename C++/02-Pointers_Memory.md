# Pointers & Memory

Pointers are a foundational and powerful feature of C++ that enable direct manipulation of memory addresses. This note explains pointer fundamentals, memory management, and common pitfalls to avoid for beginners.

---

## 1. What is a Pointer?
A pointer is a special variable that stores the **memory address** of another variable (instead of storing a direct value). Every variable in C++ resides at a unique memory address (represented as a hexadecimal number like `0x7ffeefbff5c4`).

### Key Symbols for Pointers
| Symbol       | Name               | Purpose                                                                 |
|--------------|--------------------|-------------------------------------------------------------------------|
| `&` (Ampersand) | Address-of Operator | Retrieves the memory address of a variable                              |
| `*` (Asterisk) | Dereference Operator | Accesses the value stored at the memory address held by a pointer       |

### Basic Pointer Workflow
```cpp
#include <iostream>
using namespace std;

int main() {
    // Step 1: Define a regular variable
    int num = 42;
    cout << "1. Value of num: " << num << endl;          // Output: 42
    cout << "2. Address of num: " << &num << endl;       // Output: 0x7ffeefbff5c4 (example address)

    // Step 2: Declare a pointer (type must match the target variable)
    // Syntax: type* pointer_name;
    int* ptr;  

    // Step 3: Assign the address of num to the pointer
    ptr = &num;
    cout << "3. Value of ptr (address): " << ptr << endl; // Output: Same as &num
    cout << "4. Value at ptr's address: " << *ptr << endl; // Output: 42 (dereference)

    // Step 4: Modify the original variable via the pointer
    *ptr = 99;
    cout << "5. Updated num (via pointer): " << num << endl; // Output: 99
    return 0;
}
```

---

## 2. Pointer Type Rules
Pointers are type-specific — they must match the data type of the variable they point to (for type safety):
```cpp
// Valid: int pointer points to int variable
int x = 10;
int* x_ptr = &x;

// Invalid: type mismatch (compile error)
double y = 3.14;
int* y_ptr = &y; // Error: cannot convert 'double*' to 'int*'
```

### Special Pointer Types
#### 2.1 `void*` (Generic Pointer)
A universal pointer that can point to any data type, but cannot be dereferenced directly (must be cast to a specific type first):
```cpp
int a = 5;
void* void_ptr = &a; // Valid: void* accepts any address

// Dereference after explicit casting
cout << "Value via void*: " << *(int*)void_ptr << endl; // Output: 5
```

#### 2.2 `nullptr` (Null Pointer)
A pointer that intentionally points to "nothing" (replaces the outdated `NULL` macro in C++11+). Always initialize unused pointers to `nullptr` to avoid bugs:
```cpp
// Initialize pointer to null
int* empty_ptr = nullptr;

// Check if pointer is null before use (safe practice)
if (empty_ptr == nullptr) {
    cout << "Pointer is null (no valid memory address)" << endl;
}

// WARNING: Dereferencing a null pointer causes a program crash!
// *empty_ptr = 10; // Runtime error (segmentation fault)
```

---

## 3. Memory Management (Stack vs Heap)
C++ gives you direct control over memory allocation, with two primary memory regions:

| Feature                | Stack Memory                  | Heap Memory                    |
|------------------------|-------------------------------|--------------------------------|
| Allocation/Deallocation | Automatic (by compiler)       | Manual (by programmer)         |
| Speed                  | Fast                          | Slower                         |
| Size                   | Limited (small)               | Large (system-dependent)       |
| Use Case               | Local variables, function calls | Dynamic data (arrays, objects) |

### 3.1 Dynamic Allocation with `new`
Use the `new` keyword to allocate memory on the heap (returns a pointer to the allocated memory):
```cpp
// Allocate a single integer on the heap
int* dynamic_num = new int;
*dynamic_num = 100; // Assign value to heap memory
cout << "Dynamic int value: " << *dynamic_num << endl; // Output: 100

// Allocate an array on the heap (use [] for arrays)
int* arr = new int[5]; // Array of 5 integers
// Populate the array
for (int i = 0; i < 5; i++) {
    arr[i] = i * 2; // Values: 0, 2, 4, 6, 8
}
```

### 3.2 Deallocation with `delete`
Always free heap memory with `delete` to avoid **memory leaks** (unreleased memory that accumulates over time):
```cpp
// Free a single heap variable (use delete)
delete dynamic_num;
dynamic_num = nullptr; // Set to null to avoid dangling pointer

// Free a heap array (MUST use delete[])
delete[] arr;
arr = nullptr;
```

### 3.3 Dangling Pointers (Critical Pitfall)
A dangling pointer is a pointer that points to memory that has already been deallocated (using it causes undefined behavior):
```cpp
int* ptr = new int(5);
delete ptr; // Memory is freed, but ptr still holds the old address

// ptr is now a dangling pointer
*ptr = 10; // Undefined behavior (crash, data corruption, or silent failure)
```

---

## 4. Pointers & Arrays
Arrays and pointers are interchangeable in C++ — the name of an array is a pointer to its first element:
```cpp
int numbers[3] = {10, 20, 30};

// Array name as a pointer to the first element
cout << "Array address: " << numbers << endl;       // Output: Address of numbers[0]
cout << "First element: " << *numbers << endl;      // Output: 10
cout << "Second element: " << *(numbers + 1) << endl; // Output: 20

// Iterate array with pointer arithmetic (alternative to index)
for (int i = 0; i < 3; i++) {
    cout << *(numbers + i) << " "; // Output: 10 20 30
}
```

---

## 5. Pointer to Pointer (Double Pointer)
A pointer that stores the address of another pointer (useful for nested data structures like 2D arrays):
```cpp
int value = 50;
int* ptr1 = &value;       // ptr1 points to value
int** ptr2 = &ptr1;       // ptr2 points to ptr1 (double pointer)

cout << "Value: " << value << endl;        // Output: 50
cout << "*ptr1: " << *ptr1 << endl;        // Output: 50
cout << "**ptr2: " << **ptr2 << endl;      // Output: 50
cout << "Address of ptr1: " << ptr2 << endl; // Output: Address of ptr1
```

---

## 6. Best Practices & Common Mistakes
### Safe Practices
1. Always initialize pointers (to `nullptr` if unused)
2. Check for `nullptr` before dereferencing a pointer
3. Match `new` with `delete` and `new[]` with `delete[]`
4. Set pointers to `nullptr` after deallocation

### Common Mistakes to Avoid
1. Dereferencing null/dangling pointers (crashes)
2. Memory leaks (forgetting to use `delete`/`delete[]`)
3. Type mismatches (use `static_cast` for safe conversion if needed)
4. Mixing stack and heap memory (e.g., returning a pointer to a local stack variable)

### Safe Pointer Example
```cpp
// Safe usage pattern
int* safe_ptr = new int(75);
if (safe_ptr != nullptr) { // Check before use
    cout << "Safe value: " << *safe_ptr << endl; // Output: 75
    delete safe_ptr; // Free memory
    safe_ptr = nullptr; // Avoid dangling pointer
}
