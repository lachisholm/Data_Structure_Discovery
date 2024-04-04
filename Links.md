# Linked Lists

![Linked list](LLPY.png "Header pic")

### What is a Linked List?

Linked lists are a linear data structure consisting of elements (nodes) that are linked
together using pointers or references.

A linked list is a linear data structure that stores data elements in nodes connected by pointers. The first node in a linked list is called the head node, and the last node is called the tail node. Each node has two parts:

1. The part that stores the element, the actual value or data that needs to be stored.
2. The part that stores the link to the next node in the list, creating a link between the nodes.

---

## How to define a list in Python

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

This linked list Python code above shows a class that initializes a linked list with a head property, pointing to the first node in the list.

Unlike arrays, linked lists do not require contiguous memory allocation, allowing for dynamic memory management and efficient insertion and deletion operations. Linked lists come in various forms, including singly linked lists, doubly linked lists, and circular linked lists, each offering different trade-offs in terms of memory usage and performance. They are commonly used in scenarios
where frequent insertions or deletions are expected, such as implementing stacks,
queues, or managing dynamic data structures

**A Linked list is a linear data Structure consisting of nodes, where each node contains a value and a reference( or pointer) to the next node in the sequence. Linked lists do not require contiguous memory allocation offering flexibility in storing and managing data. **

Linked lists offer flexibility in storing and managing data without needing continuous memory.There are nodes in a linked list and each node holds a value and a pointer to the next link. Linked lists can grow larger or get smaller as needed because they have the ability to allocate memory as they need too. Linked lists come in a variation of types, there is linked lists, double linked lists, and circular linked lists. Each type of list has it own way of moving through the links. What I really liked about linked lists is the way it is so easy to add or remove items, especially at the beginning or the end of the lists. This is what we call dynamic memory management and is very handy when you aren't sure how much space you will need when you first start using the list.

![Linked list](linkedlist.jpg "Linked Lists - real python")

Steps for creating a linked list

1. Create a node

```Python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

2. Connect nodes

```Python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

```

3. Append nodes

```Python
def append(self, data):
    new_node = Node(data)
    if self.head is None:
        self.head = new_node
        return
    last = self.head
    while last.next:
        last = last.next
    last.next = new_node
```

4. Insert nodes

```Python
def insert(self, prev_node, data):
    if not prev_node:
        print("Previous node must inLinkedList.")
        return
    new_node = Node(data)
    new_node.next = prev_node.next
    prev_node.next = new_node
```

5. Delete nodes by Value

```Python

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def delete_node_by_value(self, key):
        temp = self.head

        # If the list is empty
        if temp is None:
            return

        # If the node to be deleted is the head node
        if temp is not None and temp.data == key:
            self.head = temp.next
            temp = None
            return

        # Search for the node to be deleted
        while temp is not None:
            if temp.data == key:
                break
            prev = temp
            temp = temp.next

        # If the key was not present
        if temp == None:
            print("The value was not found in the list.")
            return

        # Unlink the node from the list
        prev.next = temp.next
        temp = None

```

Deleting a node by its position in the list requires a different approach

6. Delete a node by Position

```Python

    def delete_node_by_position(self, position):
        if self.head is None:
            return

        temp = self.head

        # If head needs to be removed
        if position == 0:
            self.head = temp.next
            temp = None
            return

        # Find the previous node of the node to be deleted
        for i in range(position - 1):
            temp = temp.next
            if temp is None:
                break

        # If position is more than the number of nodes
        if temp is None or temp.next is None:
            print("The position is beyond the list length.")
            return

        # Node temp.next is the node to be deleted
        # Store pointer to the next of node to be deleted
        next = temp.next.next

        # Unlink the node from the list
        temp.next = None
        temp.next = next
```

## Using a Linked List in Python

```Python
# Creating a linked list and populating it with nodes
linked_list = LinkedList()
linked_list.append(1)
linked_list.append(2)
linked_list.append(3)

# Inserting a node after the head
linked_list.insert(linked_list.head, 1.5)

# Deleting a node
linked_list.delete_node(2)
```

"A common example of a linked list is a train, all cars are connected together singly. To compare this with computer applications, the undo functionality of an application can be a linked list and the redo would be another linked list going only in one direction to the last operation." Study.com
![Train](Trains.jpg "Trains")

Adding or deleting from lists is pretty simple, quick and easy to do, while it takes just a single step. If your looking for a specific item in the list it probably will take a bit longer because you have to go through the list checking each link until you find what your looking for.

Linked Lists can also be used in creating or building out stacks and queues as well.

> **_ Stacks - While there are many different examples to what you can relate stacks to, the easiest is a stack of plates, where you can only add or remove items from the top of the stack. _**
>
> **_ Queues - like a line, you add items to the back and remove them from the front._**

---

## Challenge: Reverse a Linked List

**Task:** Implement a reverse method in the LinkedList class. This method should reverse the order of nodes in the list so that the last node becomes the first.

**Requirements:**

- Do not use any additional data structures.
- Modify the list in place.

[Back to Overview](https://github.com/lachisholm/Data_Structure_Discovery/blob/main/Overview.md)
