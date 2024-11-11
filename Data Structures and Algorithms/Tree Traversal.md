Each approach has unique characteristics but the process for each one is almost exactly the same. The only difference in their approach is how they store the nodes that need to be searched next. These nodes are known as the *frontier*.
## [[Breath-First Search]]

Is when you inspect every node on a level starting at the top of the tree and then move to the next level.

Storing the frontier nodes in a queue crates the level-by-level pattern of a breath-first search. Child nodes are searched int he order they are added to the frontier. The nodes on the next level are always behind the nodes on the current level. Breath-first search is known as a complete algorithm since no matter how deep the goal is in the tree it will always be located.
## [[Depth-first search]]
A depth-first search is where you search deep into a branch and don't move to the next one until you've reached the end.

Frontier nodes stored in a stack create the deep dive of a depth-first search. Nodes added to the frontier early on can expect to remain in the stack while their sibiling's children (and their children, and so on) are searched. Depth-first search is not consider a complete algorithm since searching an infinite branch in a tree can go on forever. In this situation, an entire section of the tree would be left un-inspected.

## [[Queues]]
The queue and the stack are the two data structures that can be used for storing nodes in a search frontier. A queue follows "First In First Out" (FIFO) behavior, where the order the data goes in the queue is the order it leaves the queue. This equates to any line you may have stood on to wait for the bus or to gran a cup of coffe.

## [[Stacks]]
A stack follows "Last In First Out" (LIFO) behavior which means that the most recent data added will be the first to leave. To get to a book at the bottom of a stack of books you must first remove the books that were more recently placed in the stack. The different behaviors of the queue and the stack will help define the behavior of the two search algorithms.

## Path to the goal
It is important to note that it is not enough to find the node with the correct value. Once the goal node is found using either method of tree traversal, you must be able to provide the path of nodes from the root node to the goal node. This can be done in many ways from saving paths as you search down the tree to working with trees that can supply path when needed.
The location of the goal node has a significant impact on determining which search algorithm will be able to find the goal first. That is why these approaches are generally used as building blocks for more complex traversal algorithms. With more information on the location of the goal value in the tree. Then they become powerful tools that can help you find that file you were looking for.