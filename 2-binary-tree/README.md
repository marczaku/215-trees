# Binary Tree

Binary Trees are an extremely important specialization of the Tree Data Structure used to bring order to things. There is different variations of the Binary Tree used for different Use-Cases: Getting the Min-Value, Getting the Max-Value or efficiently Sorting and Finding all Items.

## Overview

A binary tree is a tree where each Node has a maximum of two Child Nodes (0, 1 or 2). The tree that we saw in the previous chapter was a Binary Tree:

<img src="https://www.tutorialspoint.com/data_structures_algorithms/images/binary_tree.jpg">

## Use Cases
- Serching and Sorting (more on that later)
- Prioritizing (more on that later)
- Binary Space Partitioning: Used in 3D Games and Apps to determine what needs to be rendered
- Binary Trie: Used in Routers for routing tables
- Huffmann Coding Tree: Used in Compression like jpeg and mp3
- Syntax Tree: Used by compilers and calculators
- Treap: Used in wireless networking and memory allocation
- Hash Trees: Used in torrents and blockchains
- GGM Trees: used in cryptograhy and pseudo RNG
- Yes-No Decision Trees
- Divide-and-Conquer Algorithms

[Source](https://stackoverflow.com/questions/2130416/what-are-the-applications-of-binary-trees/2200588)

## Why Binary?

For the same reason that computers use the Binary System and why Binary Search is so relevant: it's the most easy way of splitting things up.

What if every Node had max 0 Child Nodes?
<details>
  <summary>Answer</summary>

Then it would only be one Node and not really a Data Structure.

</details>

What if every Node had max 1 Child Nodes?
<details>
  <summary>Answer</summary>

Then it would be a LinkedList.

</details>

If each Node has two Child Nodes, then you can start creating very simple rules. If-Then-Left-Else-Right and thereby bring order into the Nodes.

It is also very clearly a good Data Structure to follow the Divide-and-conquer Algorithms.

## Implementation

### Simple

```ts
define Tree<T>
   left : Tree<T>
   right : Tree<T>
   value : T
end define
```

Very obvious implementation. Works well.

### Array

```
       A(0)    
     /   \
    B(1)  C(2)  
  /   \      \
 D(3)  E(4)   F(6) 
 ```

As you can see from above graphic, you can index all elements in a Binary Tree.\
And if you can index them, you can put them into an Array, right?

For a Node with index `n`
- the left child has index `n*2+1`
- the right child has index `n*2+2`

This allows to represent a Tree like this:

```ts
define Tree<T>
   nodes : T[]
   procedure GetLeftChild(n)
      return n*2+1
   end procedure
   procedure GetRightChild(n)
      return n*2+2
   end procedure
   procedure GetValue(n)
      return nodes at index n
   end procedure
end define
```

Pro: Great performance, less cache misses
Con: Harder to read and use

The con can be mitigated by using a struct (Value-Type) like this:

```ts
define Node<T>
   index: number
   tree : Tree<T>
   procedure GetLeftChild()
      return new Node<T>
         with index: tree.GetLeftChild(index)
         and tree: tree
   end procedure
   procedure GetValue()
      return tree.GetValue(index)
   end procedure
end define
```