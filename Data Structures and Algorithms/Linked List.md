![[Pasted image 20240726233858.png]]
The list is comprised of a series of nodes.
The head node is the node at the beginning of the list. Each node contains data and a link (or pointer) to the next node in the list. The list is terminated when a node's link is `null`. This last node is called the tail node.
Consider a one-way air traveler itinerary. The trip could involve traveling through several airports (nodes) connected by air travel segments (links). In this example, the initial departure city is the head of node and the final arrival city is the tail node.
Since the nodes use links to denote the next node in the seuqence, the nodes are not required to be sequetially located in memory. These links also allow for quick insertion and removal of nodes.

Common operations on a link list may include:
- adding nodes
- removing nodes
- finding a node
- traversing (or traveling through) the linked list
![[Pasted image 20240726234417.png]]
## Adding to and Removing from the Linked List
With linked list, because nodes are linked to from only one other node, you can't just go adding and removing nodes willy-nilly without doing a bit of maintenance.
### Adding a New Node
Adding a new node to the beginning of the list requires you to link your new node to the current head node. This way, you maintain your connection with the following nodes in the list.

### Removing a Node
If you accidentally remove the single link to a node, that node's data and any following nodes could be lost to your application, leaving you with orphaned nodes.
To properly maintain the list when removing a node from the middle of a linked list, you need to be sure to adjust the link on the previous node so that it points to the following node.
Depending on the language, nodes that are not referenced are removed automatically. "Removing" a node is equivalent to removing all references to the node.
![[Pasted image 20240726235006.png]]

## Implementation
![[node#^cd318b]]

```Python
class LinkeList:
	
	def __init__(self, value = None):
		self.head_note = Node(value)
	
	def get_head_node(self):
		return self.head_node = Node(value)
	
	def get_head_node(self):
		return self.head_node
	
	def insert_ebegining(self, new_value):
		new_node = Node(new_value, self.head_node)
		self.head_node = new_node
	
	def stringify_list(self):
		itr = self.head_node
		llstr = ''
		while itr != None:
			if itr.get_value() != None:
				llstr += str (itr.get_value())+ "\n"
				itr = itr.get_next_node()
		return llstr
		
	def remove_node(self, value_to_remove):
		current_node = self.get_head_node()
		if current_node.get_value() == value_to_remove:
			self.head_node = current_node.get_next_node()
		else:
			while current_node:
				next_node = current_node.get_nex_node()
				if next_node.get_value() == value_to_remove:
					current_node.set_next_node(next_node.get_next_node())
					current_node = None
				else:
					current_node = next_node
					
		
```

