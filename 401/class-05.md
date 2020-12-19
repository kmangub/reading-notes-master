# Linked Lists

A **Linked List** is a sequence of nodes that are connected to each other where each node references the next node. A node requires two things: data and reference to the next node. There are two types of node:

- **singly** - only one node reference and it points to the next node. 
- **doubly** - points to the previous and the next node. 
- **circular** - first node is the tail and the node after is the beginning of the list.

`Current <-- Head` tells us that that we are starting from the very beginning.

To add nodes to the linked list, we need assign a value to the node and use the `AddBefore` or `AddAfter` method. Once we create the node, the next node will point to both the the assigned node and the created node, which is invalid. To remedy this, we have to change the next to point to the newly created node. 

Similar to arrays, linked lists are a type of data structure and it doesn't need to have memory allocated to it because the size and shape changes.

Big O notation for linked lists:

- O(1) takes the same amount of time and memory to run the algorithm
- O(n) is linear where the input grows and the time to calculate grows as well.

