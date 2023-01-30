# Min-Heap

https://www.tutorialspoint.com/data_structures_algorithms/images/min_heap_example.jpg![image](https://user-images.githubusercontent.com/7360266/153140583-c63e48fb-34a8-41e4-9887-e714046accd8.png)


A Min-Heap is another kind of special Binary Tree. Here, each parent's Node should be larger than each Child's Node.

## Insert

When Inserting a New Node, put it at the next available Leaf Node and then continue comparing and, if necessary, swapping it with its current Parent until its in the right place:

```
Step 1 − Create a new node at the end of heap.
Step 2 − Assign new value to the node.
Step 3 − Compare the value of this child node with its parent.
Step 4 − If value of parent is less than child, then swap them.
Step 5 − Repeat step 3 & 4 until Heap property holds.
```

This automatically balances the tree.

## Remove

Remove should always happen at the Root of the Tree, to remove the Smallest Value. You will move the lowest node up and then start swapping its way down the tree again. Again, this keeps the Tree Balanced:

```
Step 1 − Remove root node.
Step 2 − Move the last element of last level to root.
Step 3 − Compare the value of this child node with its parent.
Step 4 − If value of parent is less than child, then swap them.
Step 5 − Repeat step 3 & 4 until Heap property holds.
```