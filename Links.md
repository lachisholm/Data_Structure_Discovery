# Linked Lists

### What is a Linked List?

Linked lists are a linear data structure consisting of elements (nodes) that are linked
together using pointers or references.

A linked list is a linear data structure that stores data elements in nodes connected by pointers. The first node in a linked list is called the head node, and the last node is called the tail node. Each node has two parts:

1. The part that stores the element, the actual value or data that needs to be stored.
2. The part that stores the link to the next node in the list, creating a link between the nodes.

Unlike arrays, linked lists do not require contiguous memory allocation, allowing for dynamic memory management and efficient insertion and deletion operations. Linked lists come in various forms, including singly linked lists, doubly linked lists, and circular linked lists, each offering different trade-offs in terms of memory usage and performance. They are commonly used in scenarios
where frequent insertions or deletions are expected, such as implementing stacks,
queues, or managing dynamic data structures

**A Linked list is a linear data Structure consisting of nodes, where each node contains a value and a reference( or pointer) to the next node in the sequence. Linked lists do not require contiguous memory allocation offering flexibility in storing and managing data. **

Linked lists offer flexibility in storing and managing data without needing continuous memory.There are nodes in a linked list and each node holds a value and a pointer to the next link. Linked lists can grow larger or get smaller as needed because they have the ability to allocate memory as they need too. Linked lists come in a variation of types, there is linked lists, double linked lists, and circular linked lists. Each type of list has it own way of moving through the links. What I really liked about linked lists is the way it is so easy to add or remove items, especially at the beginning or the end of the lists. This is what we call dynamic memory management and is very handy when you aren't sure how much space you will need when you first start using the list.

![Linked list](linkedlist.jpg "Linked Lists - real python")

Steps for creating a linked list

1. Create a node
2. Connect nodes
3. Append nodes
4. Insert nodes
5. Delete nodes if applicable

![Train](trains.jpg "Trains")

"A common example of a linked list is a train, all cars are connected together singly. To compare this with computer applications, the undo functionality of an application can be a linked list and the redo would be another linked list going only in one direction to the last operation."Study.com

Adding or deleting from lists is pretty simple, quick and easy to do, while it takes just a single step. If your looking for a specific item in the list it probably will take a bit longer because you have to go through the list checking each link until you find what your looking for.

Linked Lists can also be used in creating or building out stacks and queues as well.

> **_ Stacks - While there are many different examples to what you can relate stacks to, the easiest is a stack of plates, where you can only add or remove items from the top of the stack. _**
>
> **_ Queues - like a line, you add items to the back and remove them from the front._**

[Back to Overview](https://github.com/lachisholm/Data_Structure_Discovery/blob/main/Overview.md)
