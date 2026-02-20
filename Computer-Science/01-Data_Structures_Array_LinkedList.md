# Data Structures - Array & Linked List

Arrays and Linked Lists are the most fundamental linear data structures in computer science. This note covers their definitions, implementations, pros/cons, and practical use cases in both Python and C++.

---

## 1. Array
An array is a fixed-size (or dynamic in some languages) collection of elements of the same data type, stored in contiguous memory locations.

### 1.1 Key Characteristics
- **Contiguous memory**: Elements are stored next to each other (fast random access)
- **Fixed size** (in C++): Cannot change size after creation (dynamic arrays like `vector` are exceptions)
- **Index-based access**: Access any element in O(1) time using its index (starts at 0)

### 1.2 Implementation Examples
#### Python (Dynamic List = Resizable Array)
```python
# Basic array (list) operations
# 1. Initialize an array
numbers = [10, 20, 30, 40, 50]

# 2. Access elements (O(1))
print("Element at index 2:", numbers[2])  # Output: 30

# 3. Modify elements (O(1))
numbers[1] = 25
print("Modified array:", numbers)  # Output: [10, 25, 30, 40, 50]

# 4. Insert element (O(n) - shifts elements)
numbers.insert(2, 28)
print("After insert:", numbers)  # Output: [10, 25, 28, 30, 40, 50]

# 5. Delete element (O(n) - shifts elements)
numbers.pop(3)
print("After delete:", numbers)  # Output: [10, 25, 28, 40, 50]

# 6. Array properties
print("Length:", len(numbers))  # Output: 5
print("Is empty?", len(numbers) == 0)  # Output: False
```

#### C++ (Static Array & Dynamic Vector)
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // 1. Static array (fixed size)
    int static_arr[5] = {10, 20, 30, 40, 50};
    cout << "Static array index 2: " << static_arr[2] << endl; // Output: 30

    // 2. Dynamic array (vector)
    vector<int> dynamic_arr = {10, 20, 30, 40, 50};
    dynamic_arr[1] = 25; // Modify (O(1))
    dynamic_arr.insert(dynamic_arr.begin() + 2, 28); // Insert (O(n))
    dynamic_arr.erase(dynamic_arr.begin() + 3); // Delete (O(n))

    // Iterate
    cout << "Dynamic array: ";
    for (int num : dynamic_arr) {
        cout << num << " "; // Output: 10 25 28 40 50
    }
    cout << endl;
    return 0;
}
```

### 1.3 Pros & Cons of Arrays
| Pros                          | Cons                          |
|-------------------------------|-------------------------------|
| Fast random access (O(1))     | Slow insertion/deletion (O(n))|
| Simple to implement           | Fixed size (static arrays)    |
| Cache-friendly (contiguous memory) | Wastes memory if underutilized |

---

## 2. Linked List
A linked list is a linear collection of nodes, where each node contains:
1. **Data**: The value stored in the node
2. **Pointer/Reference**: A link to the next node (and previous node for doubly linked lists)

### 2.1 Types of Linked Lists
- **Singly Linked List**: Nodes point only to the next node (traverse forward only)
- **Doubly Linked List**: Nodes point to both previous and next nodes (traverse forward/backward)
- **Circular Linked List**: Last node points back to the first node (no null end)

### 2.2 Singly Linked List Implementation
#### Python
```python
# Define a Node class
class Node:
    def __init__(self, data):
        self.data = data  # Node value
        self.next = None  # Reference to next node

# Define a Singly Linked List class
class SinglyLinkedList:
    def __init__(self):
        self.head = None  # Head (first node) of the list

    # 1. Add node to the end (append)
    def append(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            return
        last_node = self.head
        while last_node.next:  # Traverse to last node
            last_node = last_node.next
        last_node.next = new_node

    # 2. Add node to the front (prepend)
    def prepend(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    # 3. Print the list
    def print_list(self):
        current_node = self.head
        while current_node:
            print(current_node.data, end=" -> ")
            current_node = current_node.next
        print("None")

    # 4. Delete node by value
    def delete(self, key):
        current_node = self.head

        # Case 1: Delete head node
        if current_node and current_node.data == key:
            self.head = current_node.next
            current_node = None
            return

        # Case 2: Delete non-head node
        prev_node = None
        while current_node and current_node.data != key:
            prev_node = current_node
            current_node = current_node.next

        # Key not found
        if current_node is None:
            return

        # Unlink node from list
        prev_node.next = current_node.next
        current_node = None

# Usage example
llist = SinglyLinkedList()
llist.append(10)
llist.append(20)
llist.append(30)
llist.prepend(5)
llist.print_list()  # Output: 5 -> 10 -> 20 -> 30 -> None
llist.delete(20)
llist.print_list()  # Output: 5 -> 10 -> 30 -> None
```

#### C++
```cpp
#include <iostream>
using namespace std;

// Define Node class
class Node {
public:
    int data;
    Node* next;

    // Constructor
    Node(int val) : data(val), next(nullptr) {}
};

// Define Singly Linked List class
class SinglyLinkedList {
private:
    Node* head;

public:
    SinglyLinkedList() : head(nullptr) {}

    // 1. Append node to end
    void append(int data) {
        Node* new_node = new Node(data);
        if (head == nullptr) {
            head = new_node;
            return;
        }
        Node* last_node = head;
        while (last_node->next != nullptr) {
            last_node = last_node->next;
        }
        last_node->next = new_node;
    }

    // 2. Prepend node to front
    void prepend(int data) {
        Node* new_node = new Node(data);
        new_node->next = head;
        head = new_node;
    }

    // 3. Print list
    void print_list() {
        Node* current_node = head;
        while (current_node != nullptr) {
            cout << current_node->data << " -> ";
            current_node = current_node->next;
        }
        cout << "NULL" << endl;
    }

    // 4. Delete node by value
    void delete_node(int key) {
        // Case 1: Delete head
        if (head != nullptr && head->data == key) {
            Node* temp = head;
            head = head->next;
            delete temp;
            return;
        }

        // Case 2: Delete non-head
        Node* current = head;
        Node* prev = nullptr;
        while (current != nullptr && current->data != key) {
            prev = current;
            current = current->next;
        }

        // Key not found
        if (current == nullptr) return;

        // Unlink and delete
        prev->next = current->next;
        delete current;
    }

    // Destructor (free memory)
    ~SinglyLinkedList() {
        Node* current = head;
        while (current != nullptr) {
            Node* next = current->next;
            delete current;
            current = next;
        }
        head = nullptr;
    }
};

// Usage
int main() {
    SinglyLinkedList llist;
    llist.append(10);
    llist.append(20);
    llist.append(30);
    llist.prepend(5);
    llist.print_list();  // Output: 5 -> 10 -> 20 -> 30 -> NULL
    llist.delete_node(20);
    llist.print_list();  // Output: 5 -> 10 -> 30 -> NULL
    return 0;
}
```

### 2.3 Pros & Cons of Linked Lists
| Pros                          | Cons                          |
|-------------------------------|-------------------------------|
| Dynamic size (no fixed limit) | Slow random access (O(n))     |
| Fast insertion/deletion (O(1) if node is known) | More memory overhead (stores pointers) |
| No memory waste               | Not cache-friendly (non-contiguous) |

---

## 3. Array vs Linked List: When to Use?
| Use Array If...               | Use Linked List If...         |
|-------------------------------|-------------------------------|
| You need fast random access   | You need frequent insertions/deletions |
| The size is known and fixed   | The size is dynamic/unknown   |
| Memory efficiency is critical | You need to avoid element shifting |
| You are working with small datasets | You are working with large/ growing datasets |

---

## 4. Common Interview Questions
1. Reverse a linked list (iterative/recursive)
2. Detect a cycle in a linked list
3. Find the middle element of a linked list
4. Remove duplicates from a sorted array/linked list
5. Merge two sorted linked lists
