# Algorithm Fundamentals - Sorting & Searching

Algorithms are step-by-step procedures to solve problems efficiently.
This note covers the most fundamental algorithms: sorting and searching, with implementations in Python and C++.

---

## 1. What is an Algorithm?
An algorithm is a finite sequence of well-defined, computer-implementable instructions to solve a problem or perform a computation.

### Key Properties
- **Correctness**: Produces the right output
- **Efficiency**: Uses minimal time and space
- **Termination**: Finishes in finite steps

### Complexity Notation
- **Time Complexity**: How fast the algorithm runs
- **Space Complexity**: How much memory it uses
- Common notations:
  - O(1): Constant
  - O(n): Linear
  - O(log n): Logarithmic
  - O(n²): Quadratic
  - O(n log n): Linearithmic

---

## 2. Searching Algorithms

### 2.1 Linear Search
Check every element one by one.
- **Time**: O(n)
- **Use**: Unsorted data

#### Python
```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

arr = [3, 1, 4, 1, 5, 9]
print(linear_search(arr, 5))  # 4
```

#### C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int linear_search(vector<int>& arr, int target) {
    for (int i = 0; i < arr.size(); i++) {
        if (arr[i] == target)
            return i;
    }
    return -1;
}

int main() {
    vector<int> arr = {3,1,4,1,5,9};
    cout << linear_search(arr,5) << endl; // 4
    return 0;
}
```

---

### 2.2 Binary Search
Only for **sorted** data.
Divide the search space in half each time.
- **Time**: O(log n)

#### Python
```python
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

arr = [1,3,4,5,7,9,11]
print(binary_search(arr,7)) # 4
```

#### C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int binary_search(vector<int>& arr, int target) {
    int left = 0, right = arr.size()-1;
    while (left <= right) {
        int mid = (left + right)/2;
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid -1;
    }
    return -1;
}

int main() {
    vector<int> arr = {1,3,4,5,7,9,11};
    cout << binary_search(arr,7) << endl; //4
    return 0;
}
```

---

## 3. Sorting Algorithms

### 3.1 Bubble Sort
Repeatedly swap adjacent elements if in wrong order.
- **Time**: O(n²)
- **Use**: Teaching only (very slow)

#### Python
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr

arr = [64,34,25,12,22,11,90]
print(bubble_sort(arr))
```

---

### 3.2 Selection Sort
Find the minimum element and place it at the front.
- **Time**: O(n²)

#### Python
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr
```

---

### 3.3 Insertion Sort
Build sorted array one element at a time.
- **Time**: O(n²)
- **Good for nearly sorted data**

#### Python
```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >=0 and arr[j] > key:
            arr[j+1] = arr[j]
            j -=1
        arr[j+1] = key
    return arr
```

---

### 3.4 Merge Sort
Divide & conquer algorithm.
- **Time**: O(n log n)
- **Stable sort**

#### Python
```python
def merge_sort(arr):
    if len(arr) <=1:
        return arr
    mid = len(arr)//2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    res = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            res.append(left[i])
            i +=1
        else:
            res.append(right[j])
            j +=1
    res.extend(left[i:])
    res.extend(right[j:])
    return res
```

---

### 3.5 Quick Sort
Fastest general-purpose sort.
- **Time**: O(n log n) average, O(n²) worst

#### Python
```python
def quick_sort(arr):
    if len(arr) <=1:
        return arr
    pivot = arr[len(arr)//2]
    left = [x for x in arr if x < pivot]
    mid = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + mid + quick_sort(right)
```

---

## 4. Sorting Comparison
| Algorithm      | Time (Best) | Time (Avg) | Time (Worst) | Space | Stable |
|----------------|-------------|------------|--------------|-------|--------|
| Bubble Sort    | O(n)        | O(n²)      | O(n²)        | O(1)  | Yes    |
| Selection Sort | O(n²)       | O(n²)      | O(n²)        | O(1)  | No     |
| Insertion Sort | O(n)        | O(n²)      | O(n²)        | O(1)  | Yes    |
| Merge Sort     | O(n log n)  | O(n log n) | O(n log n)   | O(n)  | Yes    |
| Quick Sort     | O(n log n)  | O(n log n) | O(n²)        | O(log n)| No  |

---

## 5. Classic Interview Questions
1. Implement binary search (recursive & iterative)
2. Find the first/last occurrence in sorted array
3. Sort an array with quick / merge sort
4. Find duplicate numbers in an array
5. Search in rotated sorted array
6. Kth largest element
