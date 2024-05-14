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
Implement either
- a simple Binary Search Tree `TurboBinarySearchTree` (Easy)
- or a `TurboBinarySearchTree<T> where T:IComparable<T>` (C#, Hard)
- or a `template<typename T>` (C++, Medium)

Either way: without Balancing Algorithms. It should have these methods:

- `void Insert(T)` (inserts a new item into the tree)
- `bool Search(T)` (returns `true` if found)
- `bool Delete(T)` (returns `true` if found and deleted), 
- Iterator Pattern: returns all items in order, from min to max
  - Think about, which Traversal method you need to use
  - In C#, think about using `yield` in combination with `IEnumerable<T>` and `GetEnumerator()`
  - In C++, think about using `vector` in combination with `Iterator begin()` and `Iterator end()`

Use case example:
```csharp
TurboBinarySearchTree tree = new();

// fill the tree with a lot of even numbers
for(int i = 0; i < 1000000; i+=2){
  tree.Insert(i);
}

Debug.Log("Found 50000: " + tree.Search(50000)); // should return true
Debug.Log("Deleted 50000: " + tree.Delete(50000)); // should return true
Debug.Log("Found 50000: " + tree.Search(50000)); // should return false
Debug.Log("Found 50001: " + tree.Search(50001)); // should return false
Debug.Log("Deleted 50001: " + tree.Delete(50001)); // should return false
Debug.Log("Found 50001: " + tree.Search(50001)); // should return false

// this number is now in the tree twice
tree.Insert(50002);
Debug.Log("Found 50002: " + tree.Search(50002)); // should return true
Debug.Log("Deleted 50002: " + tree.Delete(50002)); // should return true
Debug.Log("Found 50002: " + tree.Search(50002)); // should return true
Debug.Log("Deleted 50002: " + tree.Delete(50002)); // should return true
Debug.Log("Found 50002: " + tree.Search(50002)); // should return false
```

## Excellent Criteria
- Reverse Iterator Pattern: returns all items in reverse order, from max to min
  - In C#, you can use the signature `IEnumerator<T> GetReverseEnumerator()`
  - In C++, you can use the signature `Iterator rbegin()` and `Iterator rend()`
- `Clone`: creates a clone of the tree
- `Delete`: deletes the tree, but node by node (set the value to 0, then set left to `null` and right to `null`)

## Bonus 1 (Medium)
Implement the Tree using an `Array` to store all values instead of `Node`-classes.

## Bonus 2 (Very Difficult!)

Try yourself at a Balancing Binary Search Tree implementation
