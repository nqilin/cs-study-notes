# Data Structures - Stack & Queue

Stack and Queue are two fundamental linear data structures that follow specific access rules. They are widely used in algorithm design, function calls, task scheduling, and system implementation.

---

## 1. Stack
A **Stack** is a data structure that follows the **LIFO (Last In First Out)** principle.
The last element added is the first one to be removed.

### 1.1 Basic Operations
- `push(x)`: Add element x to the top
- `pop()`: Remove and return the top element
- `top()` / `peek()`: Return the top element without removing it
- `isEmpty()`: Check if the stack is empty
- `size()`: Return the number of elements

### 1.2 Stack Implementation in Python
```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.isEmpty():
            return self.items.pop()
        return None

    def top(self):
        if not self.isEmpty():
            return self.items[-1]
        return None

    def isEmpty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Example
if __name__ == "__main__":
    s = Stack()
    s.push(10)
    s.push(20)
    s.push(30)
    print(s.top())    # 30
    print(s.pop())    # 30
    print(s.top())    # 20
```

### 1.3 Stack in C++ (STL)
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> st;

    st.push(10);
    st.push(20);
    st.push(30);

    cout << st.top() << endl;    // 30
    st.pop();
    cout << st.top() << endl;    // 20
    cout << st.size() << endl;   // 2
    return 0;
}
```

### 1.4 Common Applications
- Function call stack
- Undo/redo in editors
- Parentheses matching
- Expression evaluation (postfix/prefix)
- Depth-First Search (DFS)

---

## 2. Queue
A **Queue** follows the **FIFO (First In First Out)** principle.
The first element added is the first one to be removed.

### 2.1 Basic Operations
- `enqueue(x)`: Add element to the rear
- `dequeue()`: Remove element from the front
- `front()`: Get the front element
- `rear()` / `back()`: Get the last element
- `isEmpty()`: Check if empty
- `size()`: Return number of elements

### 2.2 Queue Implementation in Python
```python
class Queue:
    def __init__(self):
        self.items = []

    def enqueue(self, item):
        self.items.append(item)

    def dequeue(self):
        if not self.isEmpty():
            return self.items.pop(0)
        return None

    def front(self):
        if not self.isEmpty():
            return self.items[0]
        return None

    def rear(self):
        if not self.isEmpty():
            return self.items[-1]
        return None

    def isEmpty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Example
if __name__ == "__main__":
    q = Queue()
    q.enqueue(10)
    q.enqueue(20)
    q.enqueue(30)
    print(q.front())   # 10
    print(q.dequeue()) # 10
    print(q.front())   # 20
```

### 2.3 Queue in C++ (STL)
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    q.push(10);
    q.push(20);
    q.push(30);

    cout << q.front() << endl;   // 10
    q.pop();
    cout << q.front() << endl;   // 20
    cout << q.size() << endl;    // 2
    return 0;
}
```

### 2.4 Common Applications
- Task scheduling
- BFS (Breadth-First Search)
- Printer spooling
- Message queues
- Customer service systems

---

## 3. Stack vs Queue Comparison
| Feature         | Stack                  | Queue                      |
|-----------------|------------------------|----------------------------|
| Rule            | LIFO                   | FIFO                       |
| Insert Position | Top                    | Rear                       |
| Delete Position | Top                    | Front                      |
| Pointers        | Only top               | Front and rear             |
| Main Uses       | DFS, recursion, undo   | BFS, scheduling, ordering  |

---

## 4. Classic Interview Questions
1. Implement a stack using queues
2. Implement a queue using stacks
3. Valid parentheses
4. Min stack
5. Next greater element
6. Implement a circular queue
