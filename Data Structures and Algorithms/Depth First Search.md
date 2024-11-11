Depth-First Search is an algorithm used for searching tree data structures for a particular node, or node with a particular value associated with it. Depth- Frist Search is also more generally used as a tree traversal algorithm, specifying an order in which to exhaustively access all nodes of a tree. The algorithm begins at the root node and explores deeper into the tree until it reaches a leaf node. Only then will it back.track up the tree until it finds an unexplored child node. This process continues until the desired node is found, or all nodes have been explored.

There is an intuitive recursive implementation of this algorithm. But this search method can also be implemented with an iterative method that uses a stack to store roots of unexplored subtrees.
In Depth-First Search we traverse the tree vertically, from parent to child, before exploring any sibilings of that parent. Depth-First Search is an exhaustive search and this will find the targeted node if it exist in the tree. This, however, has practical implications. If a search tree is very large, or infinite in size, the Depth-First Search algorithm may never halt.

## Recursive implementation
The recursive version of the algorithm works by starting at the root node, and breaking the tree up into subtrees, until it finds the target node, or until every node in the tree has been consiered as the rrot of a subtree. We recursively call the function on all of our root's children, treating each child node as a root of its own subtree. WE define a function that accepts a tree node and a target value as input parameters. The recursive DFS algorithm implements the following logic:
- If the input node value matches our target value, then return the input node.
- For each child of the input node, recursively call this function and return the first non-null value returned by a recursive call.
- If the rrot node has no children, or recursive calls did not return any node, then return null.

To search a tree with this function, we invoke the function with the root node of our tree.

## Iterative Implementation
The iterative algorithm does nor make use of any recursive calls. Instead, we maintain a stack of references to unexplored siblings of the nodes we have already accessed. The recursive algorithm is effectively doing something very similar, but the program call stack is simply used to store the path from the root to the current node. With the iterative algorithm, we need to implement a stack ourselves. These two implementations have the same time and space complexity, so the coice of which to implement is usuallya matter of personal preference.

## Complexity
Depth-First Search has a time complexity of [[Asymptotic notation]] `O(n)` where n is the number of nodes in the tree. In the worst case, we will examine every node of a tree.
Depth-First Search has a space complexity of `O(n)` where n is the number of nodes in the tree. In the worst case, we will need to store a reference to every node in a stack. Consider an adversarial example of a linked list as a type of tree with no branching. Trees Line this could reack the worst-case space complexity if the target node is the leaf node or is absent from the tree altogether.

## Practical Considerations
DFS is a popular tree search algorithm for its intuitive and concise implementations. Depth-First search, and otrher tree traversal algorithms like it, can be found in many modern applications. DFS can be used for searching for objects in a data structures like files in a file system. More abstract applications can be found in domains like artificial intelligence, for example searching through possible moves in a game like chess, or searching for a path through a maze.
Depth-First Search is an exhaustive method, so consider that some trees may be infinitely large or just large enough that they are practically impossible to completely traverse. In practice, we can limit the depth allowed to search by the algorithm. Consider something like an algorithm for playing chess. We can simulate a series of moves and responses, but the search space may be so large that no modern computer could reasonably explore all paths.


From the following implementation of a tree:
```Python
from collections import deque

class TreeNode:
  def __init__(self, value):
    self.value = value # data
    self.children = [] # references to other nodes

  def __repr__(self):
    return self.value

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

def print_tree(root):
  stack = deque()
  stack.append([root, 0])
  level_str = "\n"
  prev_level = 0
  level = 0
  while len(stack) > 0:
    prev_level = level
    node, level = stack.pop()

    if level > 0 and len(stack) > 0 and level <= stack[-1][1]:
      level_str += "   "*(level-1)+ "├─"
    elif level > 0:
      level_str += "   "*(level-1)+ "└─"
    level_str += str(node.value)
    level_str += "\n"
    level+=1
    for child in node.children:
      stack.append([child, level])
  print(level_str)
  
def print_path(path):
  # If path is None, no path was found
  if path == None:
    print("No paths found!")  
  # If a path was found, print path
  else:  
    print("Path found:")
    for node in path:
      print(node.value)

  


sample_root_node = TreeNode("A")
two = TreeNode("B")
three = TreeNode("C")
sample_root_node.children = [three, two]
four = TreeNode("D")
five = TreeNode("E")
six = TreeNode("F")
seven = TreeNode("G")
two.children = [five, four]
three.children = [seven, six]
```


# DFS implementation
We can implement a function to find a specific node inside the tree:
```python
def dfs(root, target, path=()):
  path = path + (root,)

  if root.value == target:
    return path
    
  for child in root.children:
    path_found = dfs(child, target, path)

    if path_found is not None:
      return path_found
      
  return None
```

