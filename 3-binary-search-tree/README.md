# Binary Search Tree

<img src = "https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_tree.jpg">

A Binary Search Tree is a special kind of Binary Tree in which for each node, the following condition is true:
- all nodes on the left side of the node are smaller
- all nodes on the right side of the node ar larger

## Use Cases
- Sorted Lists
- Binary Search

## Basic Operations
- Insert
- Search
- Delete

### Search

Searching works very similar to Binary Search in a sorted collection. But instead of calculatung the next indes as the average between `min` and `max`, we just need to choose the `left` or `right` child on each node:

```
If root.data is equal to search.data
   return root
else
   while data not found

      If data is greater than node.data
         goto right subtree
      else
         goto left subtree
         
      If data found
         return node
	 
      If there is no subtree
         return data not found
   endwhile
   
end if
```

<details>
  <summary>What's the Complexity?</summary>

O(log n) - for the same reasons as we learned in Binary Search.*

*under certain conditions

</details>

### Insert

Basically just a Search where the new Node is put where the searched node would have been expected:

```
If root is NULL 
   then create root node
return

If root exists then
   compare the data with node.data
   
   while until insertion position is located

      If data is greater than node.data
         goto right subtree
      else
         goto left subtree

   endwhile 
   
   insert data
	
end If  
```

<details>
  <summary>What's the Complexity?</summary>

O(log n) - again, we perform a binary search..*

*under certain conditions

</details>

### Delete
- Disconnect the Node
- Traverse all children of the Node (which is a Sub-Tree)
- Insert all Nodes back into the Tree

<details>
  <summary>What's the Complexity?</summary>

O(n) - In worst case, we delete the root node and have to construct a completely new tree.

</details>

### Delete Better

There is better methods for deleting a Node. They cover a few cases:

- If the Node has no children: Just remove it.
- If the Node has one child: Replace the node with the child node.
- Else: Search either for the Maximum of the left sub-tree (go left and then always right until you find a leaf) or the Minimum of the right sub-tree (go right and then always left) and replace the node with the leaf you just found.

## Traversal

Traversal describes the sequence in which you can iterate over all of nodes of a Tree (or a Sub-Tree). There is four common ones:

### Preorder Traversal
Also: Depth-First-Traversal

```
Traverse(node n)
   Visit(n)
   Traverse(n.left)
   Traverse(n.right)
```

Output: `7, 2, 0, 3, 4, 11, 8, 15`

Used to Clone a Tree, Prefix-Expression

### Inorder Traversal
Also: Symmetric Traversal

```
Traverse(node n)
   Traverse(n.left)
   Visit(n)
   Traverse(n.right)
```

Output: `0, 2, 3, 4, 7, 8, 11, 15`

Used to Run through Nodes in Correct Order

### Postorder Traversal

```
Traverse(node n)
   Traverse(n.left)
   Traverse(n.right)
   Visit(n)
```

Output: `0, 4, 3, 2, 8, 15, 11, 7`

Used to Run through Leaves First, Delete a Tree, Postfix-Expressions

### Levelorder Traversal

```
Traverse(node n)
   queue.push(n)
   while(queue is not empty)
      m = queue.pop()
      Visit(m)
      queue.push(m.left)
      queue.push(m.right)
   end while
```

Output: `7, 2, 11, 0, 3, 8, 15, 4`

Use Cases: Find shortest path between two nodes, Serialization of a Tree

### Reverse Inorder Traversal
Also: Symmetric Traversal

```
Traverse(node n)
   Traverse(n.right)
   Visit(n)
   Traverse(n.left)
```

Output: `15, 11, 8, 7, 4, 3, 2, 0`

Used to Run through Nodes in Reverse Order

### Other Reverses

- Reverse Preorder Traversal
- Reverse Postorder Traversal
