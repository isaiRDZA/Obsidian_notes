Since singly linked list only have pointers from each node to its next node, swapping two nodes in the list ins't as easy as doing so in an array (where you have access to the indices). You not only have to find the elements, but also reset their surrounding pointers to maintain the integrity of the list. This means keeping track of the two nodes to be swapped as well as the nodes preceding them.
Given a linked list and the elements to be swapped (val1 and val2), we need to keep track of four values:
- node1: the node that matches val1
- node1_prev: node1's previous node
- node2: the node that matches val2
- node2_prev: node2's previous node

Given an input of a linked list, val1 and val2, the general steps for doing so is as follows:
1. Iterate through the list looking for the node that matches val1 to be swapped (node1), keeping track of the node's previous node as you iterate (node1_prev)
2. Repeat step 1 looking for the node that matches val2 (giving you node2 and node2_prev)
3. If node1_prev is None, node1 was the head of the list, so set the list's head to node2
4. Otherwise, set node1_prev's next node to node2
5. If node2_prev is None, set the list's head to node1
6. Otherwise, set node2_prev's next node to node1
7. Set node1's next node to node2's next node
8. Set node2's next node to node1's next node

## Finding the Matching and Preceding Nodes

Let's look at what implementing steps 1 and 2 looks like. In order to swap the two nodes, we must first find them. We also need to keep track of the nodes that precede them so that we can properly reset their pointers. (We will use the Node class's .get_next_node() method in order to access the next node)
We will start by setting node1 equal to the head of the list, and then creating a while loop that runs while node1 isn't None. Inside the loop, we will check if node1's value matches val1. If so, we break out of the loop as we have found the correct node. If there is no match we update node1_prev to be node1 and move node1 to its next node:
```Python
def swap_nodes(input_list, val1, val2):
	node1 = input_list.head_node
	node2 = input_list.head_node
	node1_prev = None
	node2_prev = None

	while node1 is not None:
		if node1.get_value() = val1:
			break
		node1_prev = node1
		node1 = node1.get_next_node()
		
```
At the end of this we have found out matching node, and also saved its previous node which we will use in the next step.

```Python
while node2 is not None:
	if node2.get_value() == val2:
		break

	node2_prev = node2
	node2 = node2.get_next_node()
```
## Updating the Preceding Node's Pointers

Our next step is to set node1_prev and node2_prev's next nodes, starting with node1_prev. We'll being by checking if node1_prev is None. If it is, then node1 is the head of the list, and so we will update the head to be node2. If node1_prev isn't None, then we set its next node to node2:

```Python
if node1_prev is None:
	input_list.head_node =  node2
else:
	node1_prev.set_next_node(node2);
```

After this step, we have finished updating the pointers that point to our swapped nodes. The next step will be update the pointers from them.

```Python
if node2_prev is None:
	input_list.head_node = node1
else:
	node2_prev.set_next_node(node1)
```

## Updating the Node's Next Pointers

The last step is to update the pointers from node1 and node2. This is relatively simple, and mirrors a swapping function for an array in that we will use a temporary variable

```Python
temp = node1.get_next_node()
node1.set_next_node(node2.get_next_node())
node2.set_next_node(temp)
```

## Edge Cases
We have completed the basic swap algorithm in Python! However, we haven't accounted for some edge cases. What if there is no matching node for one of the inputs? The current `swap_nodes()`function will not run because we will try to access the next node of a node the is None. (Remember that our initial while loop only breaks if the matching node is found. Otherwise, it runs until the node is None.)
Thankfully this has a quick fix. We can put in an if that checks if either node1 or node2 is None. If they are, we can print a statement that explains a match was not found, and return to end the method. We can put this right after the while loops that iterate through the list to find the matching nodes:
```Python
if(node1 is None or node2 is None):
	print("Swap not possible - one or more element is not in the list")
	return
```
The last edge case is if the two nodes to be swapped are the same. While out current implementation will run without error, there's no point in executing the whole function if it isn't necessary. We can add a brief check at the beginning of the function that checks if the val1 is the same as val2, and then return to end the function:
```Python
if val1 == val2:
	print("Elements are the same - no swap needed")
	return
```

## Finished function

```Python
import Node
import LinkedList

def swap_nodes(input_list, val1, val2):
	print(f'Swapping {val1} with {val2}')

	node1_prev = None
	node2_prev = None
	node1 = input_list.head_node
	node2 = input_list.head_node

	if val1 == val2:
		print("Elements are the same - no swap needed")
		return

	wihle node1 is not None:
		if node1.get_Value() == val1:
			break
		node1_prev = node1
		node1 = node1.get_next_node()


	while node2 is not None:
		if node2.get_value() == val2:
			break
		node2_prev = node2
		node2 = node2.get_next_node()

	if(node1 is None or node2 is None):
		print("Swap not possible - one or more
		element is not in the list")
		return

	if node1_prev is None:
		input_list.head_node = node2
	else:
		node1_prev.set_next_node(node2)

	if node2_prev is None:
		input_list.head_node = node1
	else:
		node2_prev.set_next_node(node1)

	temp = node1.get_next_node()
	node1.set_next_node(node2.get_next_node())
	node2.set_next_node(temp)

	ll = Linkedlist.Linkedlist()
	
```