# Tree

A tree is a hierarchical Data Structure with one Root Node. It is used whenever you want to structure Data in a way that there is a clear Ownership or Association of the children nodes by a parent node. Trees are also used to structure objects hierarchically.

<img src="https://www.tutorialspoint.com/data_structures_algorithms/images/binary_tree.jpg">

## Use-Cases
- Hierarchies of GameObjects
- Class-Inheritance Graphs
- State-Hierarchies
- Game-Trees (Game-State Trees following Decisions)
- Basically anything with a hierarchical 1-to-n order
- More use cases are covered by more Specialized Trees

## Terms
- **Root** the node at the top of the tree, the only node without a parent
- **Level** the generation of a node, as in the distance of a node to the root
- **Parent** the node on the higher level that is connected with the node
- **Children** the nodes on the lower level that are connected with the node
- **Leaf** a node without children
- **Subtree** a node and all of its descendants form a sub-tree
- **Visiting** refers to checking the value of a node
- **Traversing** passing through nodes in a specific order
- **Path** sequence of Nodes along the edges of a Tree

## Implementation

Implementing a tree is quite simple. The fact that connections only go in one direction makes the implementation much easier:

### Minimalistic

```ts
define Tree<T>
   children : Tree<T>[]
   value : T
end define
```

That's it. Wait, why did I not create a class named Node? Well, because technically, every Node which has children is a sub-tree. That's why I chose to not really make a difference here between Trees, Nodes and Leaves.

<details>
  <summary>What Unity Class is implemented like this?</summary>

Then it would only be one Node and not really a Data Structure.

</details>
=> Unity's `Transform`-Classs is implemented like this.

### More Detailed

If it's important to you to have "empty" Trees, then you could differentiate the two classes:

```ts
define Tree<T>
   root : Node<T>
end define

define Node<T>
   Node<T>[] children
   value : T
end define
```

=> You could argue that `Tree<T>` is like Unity's `Scene` and `Node<T>` is Unity's `Transform`.

### Further information
Very often, you still want to have some more comfort functions to make working with Nodes a bit easier. For example, it's quite useful, if the Node also knows it sparent. This is of course redundant information (because the parent knows its child, if the child also knows its parent, then the "same" information is stored in two places. This is usually considered dangerous, as you might forget to update the information in one place and then you have out-of-sync information), but it makes working with Trees much easier.

Without this information, if you happen to have a reference to a child and want to know its parent, you'd have to search the whole Tree until you find a Node that has this node as a child.

=> Again, Unity's `Transform`-Class also has this feature.