# Data Structures - Tree & Graph

Trees and Graphs are non-linear data structures that store elements in a hierarchical or interconnected manner. They are essential for solving complex problems like pathfinding, hierarchical data management, and network analysis.

---

## 1. Tree
A tree is a connected acyclic graph (no cycles) with a root node and child nodes forming a hierarchy.

### 1.1 Key Terminology
| Term          | Definition                                                                 |
|---------------|-----------------------------------------------------------------------------|
| Root          | Topmost node (no parent)                                                    |
| Node          | Basic unit (contains data + references to children)                         |
| Parent/Child  | A node directly above/below another node                                   |
| Leaf          | Node with no children                                                       |
| Depth         | Number of edges from root to node                                           |
| Height        | Number of edges from node to deepest leaf                                   |
| Subtree       | A tree formed by a node and all its descendants                             |

### 1.2 Binary Tree (Most Common Tree Type)
A binary tree is a tree where each node has at most 2 children (left and right).

#### Python Implementation (Binary Tree)
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class BinaryTree:
    def __init__(self):
        self.root = None

    # 1. Pre-order traversal (Root → Left → Right)
    def preorder(self, node):
        if node is None:
            return []
        return [node.val] + self.preorder(node.left) + self.preorder(node.right)

    # 2. In-order traversal (Left → Root → Right)
    def inorder(self, node):
        if node is None:
            return []
        return self.inorder(node.left) + [node.val] + self.inorder(node.right)

    # 3. Post-order traversal (Left → Right → Root)
    def postorder(self, node):
        if node is None:
            return []
        return self.postorder(node.left) + self.postorder(node.right) + [node.val]

# Example Usage
if __name__ == "__main__":
    # Build a simple binary tree
    tree = BinaryTree()
    tree.root = TreeNode(1)
    tree.root.left = TreeNode(2)
    tree.root.right = TreeNode(3)
    tree.root.left.left = TreeNode(4)
    tree.root.left.right = TreeNode(5)

    print("Pre-order:", tree.preorder(tree.root))  # [1,2,4,5,3]
    print("In-order:", tree.inorder(tree.root))    # [4,2,5,1,3]
    print("Post-order:", tree.postorder(tree.root))# [4,5,2,3,1]
```

#### C++ Implementation (Binary Tree)
```cpp
#include <iostream>
#include <vector>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

class BinaryTree {
public:
    // Pre-order traversal
    void preorder(TreeNode* node, vector<int>& result) {
        if (node == nullptr) return;
        result.push_back(node->val);
        preorder(node->left, result);
        preorder(node->right, result);
    }

    // In-order traversal
    void inorder(TreeNode* node, vector<int>& result) {
        if (node == nullptr) return;
        inorder(node->left, result);
        result.push_back(node->val);
        inorder(node->right, result);
    }

    // Post-order traversal
    void postorder(TreeNode* node, vector<int>& result) {
        if (node == nullptr) return;
        postorder(node->left, result);
        postorder(node->right, result);
        result.push_back(node->val);
    }
};

// Example Usage
int main() {
    // Build binary tree
    TreeNode* root = new TreeNode(1);
    root->left = new TreeNode(2);
    root->right = new TreeNode(3);
    root->left->left = new TreeNode(4);
    root->left->right = new TreeNode(5);

    BinaryTree tree;
    vector<int> res;

    tree.preorder(root, res);
    cout << "Pre-order: ";
    for (int num : res) cout << num << " "; // 1 2 4 5 3
    cout << endl;

    res.clear();
    tree.inorder(root, res);
    cout << "In-order: ";
    for (int num : res) cout << num << " ";  // 4 2 5 1 3
    cout << endl;

    res.clear();
    tree.postorder(root, res);
    cout << "Post-order: ";
    for (int num : res) cout << num << " "; // 4 5 2 3 1
    cout << endl;

    // Clean up memory
    delete root->left->left;
    delete root->left->right;
    delete root->left;
    delete root->right;
    delete root;

    return 0;
}
```

### 1.3 Common Tree Types
- **Binary Search Tree (BST)**: Left subtree < root < right subtree (for fast lookup/sort)
- **AVL Tree**: Self-balancing BST (height difference ≤1)
- **Red-Black Tree**: Self-balancing BST (used in C++ `map`/`set`)
- **Heap**: Complete binary tree (min-heap/max-heap)

---

## 2. Graph
A graph is a collection of nodes (vertices) connected by edges. Unlike trees, graphs can have cycles and unconnected nodes.

### 2.1 Key Terminology
| Term          | Definition                                                                 |
|---------------|-----------------------------------------------------------------------------|
| Vertex (V)    | Node in the graph                                                           |
| Edge (E)      | Connection between two vertices                                             |
| Directed      | Edges have direction (e.g., A → B ≠ B → A)                                 |
| Undirected    | Edges have no direction (e.g., A-B = B-A)                                   |
| Weighted      | Edges have a value/cost                                                     |
| Adjacency     | Two vertices connected by an edge                                           |
| Path          | Sequence of vertices connected by edges                                     |
| Cycle         | Path that starts and ends at the same vertex                                |

### 2.2 Graph Representations
#### 2.2.1 Adjacency List (Most Common)
Efficient for sparse graphs (few edges):
```python
# Python: Adjacency List (Undirected Graph)
class Graph:
    def __init__(self):
        self.adj_list = {}

    def add_vertex(self, vertex):
        if vertex not in self.adj_list:
            self.adj_list[vertex] = []

    def add_edge(self, v1, v2):
        # Add edge v1 ↔ v2 (undirected)
        self.add_vertex(v1)
        self.add_vertex(v2)
        self.adj_list[v1].append(v2)
        self.adj_list[v2].append(v1)

    # Depth-First Search (DFS)
    def dfs(self, start):
        visited = set()
        result = []

        def dfs_helper(vertex):
            if vertex not in visited:
                visited.add(vertex)
                result.append(vertex)
                for neighbor in self.adj_list[vertex]:
                    dfs_helper(neighbor)

        dfs_helper(start)
        return result

    # Breadth-First Search (BFS)
    def bfs(self, start):
        visited = set()
        queue = [start]
        visited.add(start)
        result = []

        while queue:
            current = queue.pop(0)
            result.append(current)
            for neighbor in self.adj_list[current]:
                if neighbor not in visited:
                    visited.add(neighbor)
                    queue.append(neighbor)

        return result

# Example Usage
if __name__ == "__main__":
    g = Graph()
    g.add_edge(0, 1)
    g.add_edge(0, 2)
    g.add_edge(1, 3)
    g.add_edge(2, 3)

    print("DFS from 0:", g.dfs(0))  # [0,1,3,2] (order may vary)
    print("BFS from 0:", g.bfs(0))  # [0,1,2,3]
```

#### 2.2.2 Adjacency Matrix
Efficient for dense graphs (many edges):
```python
# Python: Adjacency Matrix (Directed Graph)
class GraphMatrix:
    def __init__(self, num_vertices):
        self.V = num_vertices
        self.matrix = [[0]*self.V for _ in range(self.V)]

    def add_edge(self, v1, v2, weight=1):
        # Add directed edge v1 → v2
        self.matrix[v1][v2] = weight

    def print_matrix(self):
        for row in self.matrix:
            print(row)

# Example
g = GraphMatrix(4)
g.add_edge(0,1)
g.add_edge(0,2)
g.add_edge(1,3)
g.print_matrix()
# Output:
# [0,1,1,0]
# [0,0,0,1]
# [0,0,0,0]
# [0,0,0,0]
```

### 2.3 Graph Traversal Algorithms
- **DFS (Depth-First Search)**: Use stack/recursion (explore deep first)
- **BFS (Breadth-First Search)**: Use queue (explore wide first)
- **Dijkstra’s Algorithm**: Shortest path in weighted graph (non-negative weights)
- **Bellman-Ford**: Shortest path (supports negative weights)
- **Kruskal’s/Prim’s**: Minimum Spanning Tree (MST)

---

## 3. Tree vs Graph
| Feature         | Tree                          | Graph                        |
|-----------------|-------------------------------|------------------------------|
| Cycles          | No cycles                     | Can have cycles              |
| Connection      | Always connected              | May be disconnected          |
| Root            | Single root node              | No root node                 |
| Parent/Child    | Strict hierarchy              | No parent/child relationship |
| Edges           | n-1 edges (n nodes)           | Any number of edges          |

---

## 4. Classic Interview Questions
1. Binary tree traversal (iterative/recursive)
2. Validate Binary Search Tree (BST)
3. Find the height of a binary tree
4. DFS/BFS on graph
5. Shortest path in a graph (Dijkstra’s)
6. Detect a cycle in a graph/tree
7. Lowest Common Ancestor (LCA) of two nodes
