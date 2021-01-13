# Stack and Queues 

### Stacks

Stacks are a data structure that contains Nodes that reference the next node in the stack. The common terminology for stacks are:

1. `Push` - Nodes or items that are put into the stack are pushed
2. `Pop` - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
3. `Top` - This is the top of the stack.
4. `Peek` - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
5. `IsEmpty` - returns true when stack is empty otherwise returns false.

**FILO** is First In Last out. First item in the stack will be the last item popped out of the stack.

**LIFO** is Last In First out. Last item to be added in the stack will be the first one to be popped. 

> Pushing a Node will be O(1), no matter the length of the stack.

Steps to add a Node to the stack:

1. Create an arbitrary node
2. Assign next node we created to be the top stack
3. Assign the `top` to the node we created.

Below is the Pseudo Code:
```
ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node
```

To `pop` a node from the top:
1. Create a reference called `temp` where the top of the stack is
2. Re-assign `top` to be below our soon-to-be popped node
3. Remove the next property of our popped node and then the node itself
4. Return `temp`

Pseudocode for `pop`:

```
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value
```

- `peek` is where we are checking the `top` node. 
- `isEmpty` is where we are checking if the stack `isEmpty`.

### Queue

1. `Enqueue` - Nodes or items that are added to the queue.
2. `Dequeue` - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
3. `Front` - This is the front/first Node of the queue.
4. `Rear` - This is the rear/last Node of the queue.
5. `Peek` - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
6. `IsEmpty` - returns true when queue is empty otherwise returns false.

> Adding an item to the queue is O(1) for time, regardless of the the length of the queue.

To add a node to the queue:

1. Change the `next` of the rear queue to be the node we are adding. 

2. Re-assign the rear to be the node we added.

Pseudocode for adding a node, or `enqueue`:

```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node
```

To remove a node from a queue:
1. Create a reference called `temp` and have it point to front.
2. Re-assign front to the node before the one we are removing.
3. Re-assing the next property of the node we are removing to `null`
4. return the value of `temp`

Pseudo code for removing the node, or `dequeue`:

```
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
```

- `peek` is where we are checking the `front` node. 
- `isEmpty` is where we are checking if the stack `isEmpty`.