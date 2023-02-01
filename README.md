# 204 Trees

A tree is a hierarchical Data Structure with one Root Node. It is used whenever you want to structure Data in a way that there is a clear Ownership or Association of the children nodes by a parent node. Trees are also used to structure objects hierarchically.

<img src="https://www.tutorialspoint.com/data_structures_algorithms/images/binary_tree.jpg">

## Use-Cases
- Hierarchies of GameObjects
- Class-Inheritance Graphs
- State-Hierarchies
- Game-Trees (Game-State Trees following Decisions)
- Basically anything with a hierarchical 1-to-n order
- More use cases are covered by more Specialized Trees

## Passing Criteria
Implement a simple Binary Search Tree `TurboBinarySearchTree` or `TurboBinarySearchTree<T> where T:IComparable<T>` without Balancing Algorithms. It should have these methods:

- `Insert`, `Search`, `Delete`, 
- `GetEnumerator`: returns all items in order, from min to max
- `GetInOrder`: same as GetEnumerator 
- `GetInReverseOrder`: returns all items in reverse order, from max to min
- `Clone`: creates a clone of the tree

## Excellent Criteria
- `Delete`: deletes the tree, but node by node (set the value to 0, then set left to `null` and right to `null`)
- Implement the Tree using an `Array` to store all values instead of `Node`-classes.

## Bonus (Insane)

Try yourself at a Balancing Binary Search Tree implementation
