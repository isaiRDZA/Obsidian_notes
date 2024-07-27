Nodes are the fundamental building blocks of many computer science data structures. They form the bases for [[linked list]], [[stacks]], [[ques]], [[trees]] and more.
An individual node contains data and links to other nodes. Each data structure adds additional constrains or behavior to these features to create the desired structure.
![[Pasted image 20240726232018.png]]

## Node implementation
A node can contain a variety of types of data.
The link or links within the node are sometimes referred as pointers.
Typically, data structures implement nodes with one or more links. If these links are `null`, it denotes that you have reached the end of the particular node or link path you were previously following.
![[Pasted image 20240726232245.png]]
Often,due to data structures, nodes may only be lnked to a single other node.
This makes it very important to consider how you implement modifying or removing nodes from a data structure.
If you inadvertently remove the single link to a node, that nodes's data and any linked nodes could be "lost" to your application. When this happen to a node, it is called an orphaned node.

```Python
class Node:
	def __init__(self, value, link_node = None):
		self.value = value
		self.link_node = link_node


	def get_value(self):
		return self.value
	def get_link_node(self):
		return self.link_node
	def set_link_node(self, link_node):
		self.link_node = link_node
```