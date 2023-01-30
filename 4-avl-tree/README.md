# AVL Tree / Red-Black Tree

## Degenerate Tree

Problem: If the nodes come in in a sorted (or almost sorted) order:

<img src="https://2.bp.blogspot.com/-eLQTSxHwvLw/Vb2fI3P9hZI/AAAAAAAAHp0/VzpPjaENcGk/s320/ZnJvbT1jbmJsb2dzJnVybD1nWnBkbUw0RVdPNVVqTjNnak54SVROd0lUWWlCRE80UUROMlVtWnhBVE95Z3pZMUVXTHhRRE96VVRNMkl6TDVBek14QWpNdlF6TndnRE0xOHladnhtWXYwMmJqNXladnhtWTBsbWJqNXljbGRXWXRsMkx2b0RjMFJIYQ.jpg">

That does not look like much Divide and Conquer going on here, eh?

This kind of Tree is called a degenerate Tree and as mentioned, it can happen, if the data comes in a certain ordered fashion.

In above case, the difference between a Binary Search Tree and a Linked list is actually only that the BST has some overhead. Meh!

## Balanced Tree

What we want:

<img src="https://1.bp.blogspot.com/-4V266slC8f0/Vb2fiBQVXMI/AAAAAAAAHqo/04CsmIUVky0/s1600/images%2B%25281%2529.png">

<img width="400" src="https://i.kym-cdn.com/entries/icons/original/000/027/257/perfectly-balanced-as-all-things-should-be.jpg">


## Solution:

Balanced Tree Building Approach.

This is, what Red-Black Trees and AVL Trees do.

What they do is: They use Tree Rotations to rebalance a tree whenever it appears too imbalanced.

## Tree Rotation

<img src="https://www.tutorialspoint.com/data_structures_algorithms/images/avl_left_rotation.jpg">


## Balance

### AVL Tree

<img src="https://media.geeksforgeeks.org/wp-content/uploads/AVL-Insertion1-1.jpg">

Every node has the height of the left sub-tree and the height of the right sub-tree stored. The Balance Factor is the difference of both.\
If the absolute of the difference is greater than 1, it is unbalanced and Tree Rotations need to happen in the right places to bring it back to balance.

### Red Black Tree

<img src="https://algorithmtutor.com/images/RBTreeExample.png">

Red-Black Trees give the colors Red and Black (or simply 0/1 bit) to Nodes to specify, depending on:
- the root: black
- `null` child: black
- node with two black children: red

A red tree is balanced, if each path to the root has the same amount of black Nodes.

This can lead to a tree that's twice as long on the longest than on the shortest path (shortes: all black, longest: alternating red and black)

Then, these colors are used to determine strategies for Rebalancing on Insertion and Deletion. These are just algorithms that observe the state around the new node and then start rotating around.

## Further Reading

There is an endless amount of resources on this topic. Red-Black-Trees and AVL Trees are the state of the arts if it comes to Binary Search Trees, as an unbalanced Tree has catastrophic performance impact.

Of course, the balancing comes with an overhead, but that cost is willingly paid considering how a degenerate tree could mean a lookup of 1 million ms instead of 20ms (Remember?)