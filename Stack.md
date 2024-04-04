# Practical Applications of Stack

#### **LIFO is an acronym for Last In, First Out.**

The terms LIFO and FIFO refer to two different methods of managing data structures, particularly in the context of how data is stored, accessed, and removed. These methods are fundamental to computer science and software development, especially in algoithm design and system resource management.

LIFO stands for "Last In, First Out." It is a method of managing data such that the last element added to a structure is the first one to be removed. This principle is like a stack, you can only take off the top without disturbing the others, which means the last plate you put on the stack is the first one you take off.

#### **Characteristics of LIFO**

Addition(push) New elements are added to the top of the stack.
Removal (pop) elements are removed from the top of the stack.
Top Element It's easy to see or access the top element, which is the last added item
Use Cases LIFO is particularly useful in scenarios like function call management in programming languages like a call stack, undo mechanisms in software, and for parsing certain kinds of expressions.

FIFO is an acronym for First IN, First Out. It is a method of managing data where the first element added to a structure is the first one to be removed. This is similar to a line of people whether at a grocery store or movie theather, the first person to get in line is the first one to be served and leave.

#### **Characteristics of FIFO**

Addition which is also called Enqueue. New elements are added to the end of the queue.
Removal which is also called Dequeue. Elements are removed from the beginning of the queue
Front and Rear Elements in a FIFO structure, you can easily access the first (front of line) and the last (rear of line) elements, which represent the first added and last added items.
Use Cases: FIFO is widely used in resource scheduling such as printer queues or buffering data streams, and handling asynchronous data transfers between software components.

| Aspect        | LIFO (Stack)                                        | FIFO (Queue)                                           |
| ------------- | --------------------------------------------------- | ------------------------------------------------------ |
| Order         | Last In, First Out                                  | First In, First Out                                    |
| Addition      | Added to the top                                    | Added to the end                                       |
| Removal       | Removed from the top                                | Removed from the beginning                             |
| Accessibility | Top Element only                                    | Front and rear elements                                |
| Use Cases     | Function calls, Undo operations, Expression parsing | Resource Scheduling, Buffering, Asynchronous transfers |

The LIFO concept does not directly apply to maps, linked lists, and trees however LIFO can be
associated with these data structures in the context of specific applications or operations
Starting with maps or associative arrays, which are collections of key value pairs. They do not
inherently follow a LIFO principle as they are designed for fast retrieval, insertion, and deletion
based on keys. However, you can use stacks to track the insertion order in maps if needed for
specific applications, such as undo functionality in a key value store where the most recently
added entry needs to be removed first. Linked lists themselves are not LIFO structures, you can
implement a stack using a linked list by adding and removing elements from the same end of the
list, effectively utilizing the LIFO principle in the context of linked list operations. Trees do not
intrinsically operated on a LIFO principle, but tree traversal algorithms, such as depth first search
(DFS) can utilize a stack and the LIFO principle to explore the depth of the tree first, moving
through one branch to its leaves before backtracking to explore other branches.

LIFO(Stack) Optimized for scenarios where the most recent data is of the highest priority. It is used in applications where the order of operations must be reversed or last performed operation needs to be accessed quickly.

![LIFO](LIFOdraw.jpg "Last in First out") Deposit photos

LIFO(stack)

- Push(Addition) Adds an element to the top, the effieciency is O(1)
- Pop(Removal) Removes the top element. O(1)
- Peek (Access Next) Returns the top element without removing O(1)
- IsEmpty (Check Empty): Checks if the stack is empty. O(1)

![FIFO](FIFOblock.jpg "First in and First out") Cadre Technologies

FIFO(Queue) Best suited for scenarios where the order of operations or data processing must remain consistent over time. It is used in scheduling and sequential processing tasks where the first input should be the first to be processed or executed.
FIFO(Queue)

- Enqueue(Addition): Adds an element to the end. O(1)
- Dequeue(Removal) Removes the first element O(1)
- Front (Access Next): Returns the first element without removing O(1)
- IsEmpty(Check Empty) Checks if the queue is empty O(1)

Here is a LIFO (stack Implementation)

```Python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):

        """O(1) """
        self.items.append(item)

    def pop(self):
        """O(1)"""
        if not self.is_empty():
            return self.items.pop()
        return None

    def peek(self):
        """O(1)"""
        if not self.is_empty()
            return self.items[-1]
        return None

    def is_empty(self):
        """O(1) operation"""
        return len(self.items) == 0

# Example usage
stack = Stack()
stack.push(1)
stack.push(2)
print(stack.peek())
stack.pop()
print(stack.peek())
```

Here is FIFO implementation using a collections.deque in python

```Python
from collections import deque

class Queue:
    def __init__(self):
        self.items = deque()

    def enqueue(self, item):
        """O(1)"""
        self.items.append(item)

    def dequeue(self):
        """O(1)"""
        if not self.is_empty()
        return self.items.popleft()
    return None

    def front(self):
        """O(1)"""
        if not self.is_empty():
            return self.items[0]
        return None

    def is_empty(self):
        """O(1)"""
        return len(self.items) == 0

queue = Queue()




```

Understanding and appplying the appropriate data structure based on LIFO or FIFO principles is crucial in developing efficient algorithms and systems.

[Back to Overview](https://github.com/lachisholm/Data_Structure_Discovery/blob/main/Overview.md)
