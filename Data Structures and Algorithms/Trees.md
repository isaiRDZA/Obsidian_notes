Similar to linked list and graphs, trees are composed of nodes which hold data.
Nodes also store references to zero or  more other tree nodes. Data moves down from node to node.
![[Pasted image 20241103193047.png]]

Trees grow downwards in computer science, and a root node is at the very top.
When a node has no children, we refer to it as lead node.
## Tree varietals
Trees come in various shapes and sizes depending on the dataset modeled.
Some are wide, with parent nodes referencing many child nodes.
Some are deep, with many parent-child relationships.
Trees can be both wide and deep, but each node will only ever have at most one parent; otherwise, they wouldn't be trees.
Each time we move from a parent to a child, we're moving down a level. Depending on the orientations we refer to this as the depth (counting levels down from the root node) or height  (counting levels up from a lead node).
![[Pasted image 20241103193514.png]]

## Tree implementation

```python
class TreeNode:

  def __init__(self, value):
    self.value = value # data
    self.children = [] # references to other nodes

  

  def add_child(self, child_node):
    # creates parent-child relationship
    print("Adding " + child_node.value)
    self.children.append(child_node)

  def remove_child(self, child_node):
    # removes parent-child relationship
    print("Removing " + child_node.value + " from " + self.value)
    self.children = [child for child in self.children
                     if child is not child_node]

  def traverse(self):
    # moves through each node referenced from self downwards
    nodes_to_visit = [self]
    while len(nodes_to_visit) > 0:
      current_node = nodes_to_visit.pop()
      print(current_node.value)
      nodes_to_visit += current_node.children
```
### High-Level Description

The `TreeNode` class represents a basic tree data structure in Python. Each node in the tree can hold a value and have multiple children. The class provides methods to add and remove child nodes and to traverse the tree, printing the value of each node.

### Detailed Explanation

1. **Initialization (`__init__` method):**
   - The constructor initializes a `TreeNode` with a `value` and an empty list `children` to store references to child nodes.

2. **Adding a Child (`add_child` method):**
   - This method takes a `child_node` as an argument.
   - It prints a message indicating the addition of the child.
   - The child node is appended to the `children` list, establishing a parent-child relationship.

3. **Removing a Child (`remove_child` method):**
   - This method takes a `child_node` as an argument.
   - It prints a message indicating the removal of the child.
   - The `children` list is filtered to exclude the specified `child_node`, effectively removing the parent-child relationship.

4. **Traversing the Tree (`traverse` method):**
   - This method performs a depth-first traversal of the tree.
   - It starts with the current node and uses a list `nodes_to_visit` to keep track of nodes to be visited.
   - It iteratively pops nodes from the list, prints their values, and adds their children to the list.

### Comparison with Modern Libraries

Modern libraries like `networkx` or `anytree` provide more advanced and efficient implementations of tree structures. They offer features like:

- **Ease of Use:** Simplified interfaces for creating and managing trees.
- **Performance:** Optimized algorithms for tree operations.
- **Additional Features:** Support for various tree types (e.g., binary trees, decision trees) and advanced traversal methods.
- **Visualization:** Tools for visualizing tree structures.

These libraries are more suitable for complex applications, while the `TreeNode` class is a simple, educational implementation.