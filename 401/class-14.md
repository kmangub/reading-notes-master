# Trees

Binary Trees and Binary Search Trees Terminology:

- Node - A node is the individual item/data that makes up the data structure
- Root - The root is the first/top Node in the tree
- Left Child - The node that is positioned to the left of a root or node
- Right Child - The node that is positioned to the right of a root or node
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not contain any children
- Height - The height of a tree is determined by the number of edges from the root to the bottommost node

Traversing trees allow us to print out the contents of the trees or search for a node.
We use recursion and the call stack to make this possible. There are two ways we can traverse through trees:

- Depth First, which prioritize going through the depth (height) of the tree. There are three methods:
    - Pre-order: root >> left >> right
    - In-order: left >> root >> right
    - Post-order: left >> right >> root


- Breadth First iterates through the tree by going through each level of the tree node-by-node.

Adding Nodes is as simple as adding the child from the top down, left to right. However, if we want to add the node to a specific place, we just need to reference the parent node and the new node we created. 

Searching nodes can be achieved with a while loop. We cycle through a while loop until we hit a leaf or the node is found. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side

### Pseudo Code

Pre-order:
```
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
```

In-order:
```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

Post-order:
```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```

Breadth first:
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```


