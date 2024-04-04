# Trees in Data Structures

![Tree](treealgor.jpg "Tree Structure-python by Analytics Vidhya")Analytics Vidhya

Trees are hierarchical data structures composed of nodes connected by edges. Each
node can have zero or more child nodes, forming a branching structure. Trees are
widely used for representing hierarchical relationships, such as file systems,
organization charts, or hierarchical data in databases.

Trees are a fundamental data structure in computer science with a wide range of applications.
Understanding how they work and how to manipulate them is crucial for software development and algorithm design

![Trees](Treepic.jpg "Trees")Slideserve

The topmost node is called the root, and every node(except the root) is connected by an edge from exactly one other node, known as its parent.

Like a family, nodes with the same parent are siblings, and nodes without children are called leaves.

![Tree](treestructure.jpg "Tree Structure-medium")Towardsdatascience

They also play a crucial role in algorithms and data structures, with various types of trees like binary trees, binary search trees, AVL trees, and B-trees optimized for different purposes. Trees offer efficient search, insertion, and deletion operations, making them essential in many
applications requiring organized and structured data.

A node is a basic unit of a tree.
Here is Python code to show a single node with a value

```python

class Node:
    def __init__(self, value):
        self.value = value  # Holds the data of the node

# Creating a single node with a value
single_node = Node(10)

# Displaying the value of the created node
print(f"Node value: {single_node.value}")

```

The Node class simply holds a value, and the concept of children nodes is not shown above, this is because the node is an independent unit.

When we want the node to have more than the independent unit, then we link it to children where a node contains data and links to other nodes. Each node in a tree can have zero or more child nodes.

An example of this in python could be written like this

```python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.children = []
```

- A Root is the topmost node in a tree.
  There is exactly one root per tree, and it has no parent. My code snip below shows a class where each node has a value and a list of children. The root node is then created by instantiating the TreeNode class with the value RootNode

```python

class TreeNode:
    def __init__(self, value):
        self.value = value
        self.children = []

# Here is how you create the root node
root = TreeNode("Root Node")
```

- A Leaf is a node with no children.
  Leaves are at the bottommost level of a tree
  Here is how you create a leaf node since the leaf has no children.

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.children = []

# we don't add any children to the list.
leaf = TreeNode("Leaf Node")
```

- Depth of a node is the number of edges from the root to the node.
  It is an indication of the level at which the node sits in the tree. Meaning it essentially measures how far a node is from the root. So you could also say it's the length of the path from the root to the node. The depth of the root node itself is always zero since there are no edges to traverse to reach it.

  - So let's assume a structure where each node knows its parent, allowing us to directly calculate the depth by counting how many times we can move from the node to its parent until we reach the root.

  - The TreeNode class represents each node with a value and an optional parent

  - The depth function calculates the depth by traversing up the parent chain until it finds a node without a parent, which would be the root.

  - The depth counter increments with each step up

  - The example constructs a simple tree where 'child2' is a grandchild of the 'root', making its depth 2

```python

class TreeNode:
    def __init__(self, value, parent=None):
        self.value = value
        self.parent = parent

    def depth(node):
    depth = 0
    while node.parent:
        node = node.parent
        depth += 1
    return depth

# This is how to set up a simple tree
root = TreeNode("Root")
# This is the child of the root
child1 = TreeNode("Child 1", root)
# This is the child of the child, which makes it the grandchild of the root
child2 = TreeNode("Child 2", child1)
```

- Height of a node is the number of edges on the longest path from the node to a leaf.
  The height of a tree is the height of its root node.

  - The height of a node to be the number of edges on the longest path from the node to a leaf.
  - A leaf node having no children, has a height of 0.

Here is python code that shows the treenode class represents each node, where a node can have multiple children stored in a list. The add_child method is used to establish parent child relationships. The height function calcuates the height of a node.
For a node with no children(a leaf), the height is 0
For other nodes, it recursively finds the height of each child node, selects the maximum height among them, and adds 1(representing the edge between the node and its child)

```python
class TreeNode:
    def __init__(self, value):
        self.value = value
        self.children = []

    def add-child(self, child):
        self.children.append(child)

def height(node):
    # This is the Base case, if it has no children, it's a leaf
    if not node.children:
        return 0

    else:
        # Recursive 1+ the height of the tallest child
        return 1 + max(height(child)for child in node.children)

root = TreeNode("Root")
child1 = TreeNode("Child1")
child2 = TreeNode("Child2")
leaf1 = TreeNode("Leaf 1")
leaf2 = TreeNode("Leaf 2")

root.add_child(child1)
root.add_child(child2)
child1.add_child(leaf1)
child2.add_child(leaf2)

#out puts 2, since the longest path from root to a leaf is 2 edges
print(height(root))

```

### Practical Applications of Trees in Computer Science

Trees, as a pivotal data structure, find extensive application in various computer science domains due to their hierarchical nature and efficiency in managing and organizing data.

- **Binary Search Trees (BST):** BSTs are crucial for efficient searching and sorting operations. They store data in a structured manner, where each node has a maximum of two children. This property ensures that operations like search, insert, and delete can be performed in logarithmic time complexity, making BSTs highly effective for managing sorted data.

- **File Systems:** In operating systems, trees play a fundamental role in organizing files and directories. The tree structure allows for a hierarchical organization where directories can contain files or other directories. This setup mimics a real-world filing system, facilitating efficient file storage, retrieval, and management.

- **Databases:** Trees are integral to the design of database indexing mechanisms, particularly through variants like B-trees and B+-trees. These structures enable databases to quickly locate records, significantly reducing the time required for data retrieval operations. Their ability to maintain sorted data and support efficient insertion and deletion operations makes them indispensable for database management systems seeking to optimize performance.

These applications underscore the utility of trees in enhancing data accessibility, organization, and processing across different computer science disciplines.

Here is a simple python code inserting a new node in a Binary Search Tree

```python
class BSTNode:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None

    def insert(root, key):
        if root is None:
            return BSTNode(key)
        else:
            if root.key < key:
                root.right = insert(root.right, key)
            elif root.key > key:
                root.left = insert(root.left, key)
        # If root.key is equal to key, then this key is already present in the tree,
        # so we do not insert it again. BSTs do not contain duplicate keys.
    return root

```

### Sample Use Problem

There will be many ways that you use trees in Data Structure and in programming in the real world. So let's look at one.

Suppose you're tasked with managing an inventory for a bookstore. Each book is categorized based on its genre, and within each genre, books are further organized by author name. You decide to use a tree data structure to efficiently manage and access your inventory.

The first thing you would have to do is to create a simple tree structure using your language of choice. Mine is Python. So I would create a simple tree structure in Python to represent book genres as the first level of nodes and authors as the second level. This structure will help quickly access all the books by a specific author within any genre.

How To:

First it is needed to define a "TreeNode" class to represent each node in the tree. The root nodes of the tree will represent different genres, and each genre node will have child nodes representing authors in that genre

Here is what you could do to build your structure up to the author level.

```Python

class TreeNode:
    def __init__(self, name):
        self.name = name
        self.children = []

    def add_child(self, child_node):
        self.children.append(child_node)

# This will create the root node for the tree
root = TreeNode("Bookstore")

# This will create the genre node(children of the root)
fiction =  TreeNode("Fiction")
non_fiction = TreeNode("Non-Fiction")

# Adding genre nodes to the root's children
root.add_child(fiction)
root.add_child(non_fiction)

#This is for creating authors under "Fiction"
author1 = TreeNode("Author A")
author2 = TreeNode("author B")

# Adding authors to the fiction genre
fiction.add_child(author1)
fiction.add_child(author2)

# Simple display function to show the structure
def display_tree(node, level= 0):
    print("  " * level + node.name)
    for child in node.children:
        display_tree(child, level+1)

# This is where you Display the bookstore inventory structure
display-tree(root)
```

## Your Challenge:

Make your own library now you know how to get started. Give it more than fiction, non-fiction. Choose different areas like children section, adults, teens, and give each of these their own classifications of fiction, non-fiction, adventure, the classics, and anything else that you can think of to bring your library to life for different ages.

[Back to Overview](https://github.com/lachisholm/Data_Structure_Discovery/blob/main/Overview.md)
