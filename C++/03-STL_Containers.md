# STL Containers

The Standard Template Library (STL) is a collection of template classes and functions in C++ that provides reusable data structures (containers) and algorithms. This note covers the most commonly used STL containers with practical examples.

---

## 1. What are STL Containers?
STL containers are pre-built, generic data structures that store collections of objects. They are divided into three main categories:

| Category          | Examples                          | Key Features                                  |
|-------------------|-----------------------------------|-----------------------------------------------|
| Sequence Containers | `vector`, `list`, `deque`         | Ordered collection, access by position        |
| Associative Containers | `set`, `map`, `unordered_set`, `unordered_map` | Sorted/unsorted, access by key                |
| Container Adaptors | `stack`, `queue`, `priority_queue` | Restricted access (e.g., LIFO/FIFO)           |

### Key Notes
- All STL containers are template-based (support any data type)
- Include the corresponding header file (e.g., `<vector>`, `<map>`)
- Use `std::` prefix (or `using namespace std;`)

---

## 2. Sequence Containers
### 2.1 `vector` (Dynamic Array)
The most widely used STL container — a resizable array that grows/shrinks automatically.

```c++
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // 1. Initialize a vector
    vector<int> nums; // Empty vector of ints
    vector<string> fruits = {"apple", "banana", "orange"}; // Initializer list

    // 2. Add elements (push_back adds to the end)
    nums.push_back(10);
    nums.push_back(20);
    nums.push_back(30);

    // 3. Access elements
    cout << "First element: " << nums[0] << endl; // Unchecked access (fast)
    cout << "Second element: " << nums.at(1) << endl; // Checked access (safe)
    cout << "Last element: " << nums.back() << endl; // Get last element

    // 4. Iterate over vector
    cout << "Vector elements: ";
    for (int num : nums) { // Range-based for loop (C++11+)
        cout << num << " ";
    }
    cout << endl;

    // 5. Modify elements
    nums[1] = 25; // Change second element to 25

    // 6. Vector properties
    cout << "Size: " << nums.size() << endl; // Number of elements (3)
    cout << "Capacity: " << nums.capacity() << endl; // Allocated memory (>= size)
    cout << "Empty? " << (nums.empty() ? "Yes" : "No") << endl; // Check if empty

    // 7. Remove elements
    nums.pop_back(); // Remove last element
    nums.clear(); // Remove all elements
    return 0;
}
```

### 2.2 `list` (Doubly Linked List)
A linked list that allows fast insertion/deletion at any position (but slow random access).

```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    list<int> my_list = {5, 10, 15};

    // Insert elements
    my_list.push_front(0); // Add to front (0,5,10,15)
    my_list.insert(next(my_list.begin(), 2), 7); // Insert 7 at position 2

    // Iterate (no random access with [])
    cout << "List elements: ";
    for (auto it = my_list.begin(); it != my_list.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl; // Output: 0 5 7 10 15

    // Remove elements
    my_list.remove(7); // Remove all elements with value 7
    my_list.pop_back(); // Remove last element
    return 0;
}
```

---

## 3. Associative Containers
### 3.1 `map` (Key-Value Pairs, Sorted)
Stores key-value pairs in a sorted order (keys are unique).

```cpp
#include <iostream>
#include <map>
#include <string>
using namespace std;

int main() {
    // Initialize a map (key: string, value: int)
    map<string, int> age_map;

    // Add key-value pairs
    age_map["Alice"] = 25;
    age_map["Bob"] = 30;
    age_map["Charlie"] = 28;

    // Access values
    cout << "Bob's age: " << age_map["Bob"] << endl; // Output: 30

    // Iterate over map
    cout << "\nAll entries:" << endl;
    for (const auto& pair : age_map) {
        cout << pair.first << ": " << pair.second << endl;
    }

    // Check if key exists
    string name = "Dave";
    if (age_map.find(name) == age_map.end()) {
        cout << "\n" << name << " not found" << endl;
    }

    // Remove entry
    age_map.erase("Charlie");
    return 0;
}
```

### 3.2 `unordered_map` (Hash Map)
Unsorted key-value pairs (faster access than `map` for large datasets).

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<string, string> country_capital;
    country_capital["USA"] = "Washington D.C.";
    country_capital["China"] = "Beijing";
    country_capital["Japan"] = "Tokyo";

    // Faster iteration (unsorted)
    for (const auto& pair : country_capital) {
        cout << pair.first << ": " << pair.second << endl;
    }
    return 0;
}
```

### 3.3 `set` (Unique Sorted Values)
Stores unique values in sorted order (no duplicates).

```cpp
#include <iostream>
#include <set>
using namespace std;

int main() {
    set<int> my_set = {3, 1, 4, 1, 2}; // Duplicates are removed

    // Insert element
    my_set.insert(5);

    // Iterate (sorted automatically)
    cout << "Set elements: ";
    for (int num : my_set) {
        cout << num << " "; // Output: 1 2 3 4 5
    }
    cout << endl;

    // Check if element exists
    if (my_set.count(3)) {
        cout << "3 is in the set" << endl;
    }
    return 0;
}
```

---

## 4. Container Adaptors
### 4.1 `stack` (LIFO - Last In First Out)
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> s;

    // Push elements onto stack
    s.push(10);
    s.push(20);
    s.push(30);

    // Access top element
    cout << "Top: " << s.top() << endl; // Output: 30

    // Pop element (remove top)
    s.pop();
    cout << "New top: " << s.top() << endl; // Output: 20

    cout << "Size: " << s.size() << endl; // Output: 2
    return 0;
}
```

### 4.2 `queue` (FIFO - First In First Out)
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<string> q;

    // Enqueue elements
    q.push("First");
    q.push("Second");
    q.push("Third");

    // Access front/back
    cout << "Front: " << q.front() << endl; // Output: First
    cout << "Back: " << q.back() << endl; // Output: Third

    // Dequeue element
    q.pop();
    cout << "New front: " << q.front() << endl; // Output: Second
    return 0;
}
```

---

## 5. Best Practices
1. **Choose the right container**:
   - Use `vector` for random access and fast iteration (most common choice)
   - Use `list` for frequent insertion/deletion in the middle
   - Use `map` for sorted key-value pairs, `unordered_map` for faster lookups
   - Use `stack`/`queue` for LIFO/FIFO operations

2. **Avoid unnecessary copies**: Use `const` references (`const auto&`) when iterating
3. **Check bounds**: Use `at()` for `vector` if you need bounds checking (safer than `[]`)
4. **Clear memory**: Containers automatically free memory when destroyed (no manual `delete`)
