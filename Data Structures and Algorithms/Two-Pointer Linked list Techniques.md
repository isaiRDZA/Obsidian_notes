Learn how to approach Linked List problems with multiple iterator pointers.

Many common singly linked list problems can be solved by iterating with two pointers. This is sometimes know as the runner technique.

# Two pointers Moving in Parallel

Consider the following problem:
Create a method that returns the nth last element of singly linked list.
For example: given a linked list with the following elements 1 -> 2 -> 3 -> 4 -> 5, return the 2nd to last element. Then answer would be element 4.
In order to do this, you'll need some way of knowing how far you are from the end of the list itself. However, in a singly linked list, there's no easy way to iterate back through the list when you find the end.

## Approaches
One thing that might first come to mind is to use a list to store a representation of the linked list, and then to obtain the nth to last element from this list. While this approach results in an easy-to-read implementation, it could also use up lots of memory maintaining a dual representation of the same data. If the linked list has one million nodes, we'll need one million pointers in a list to keep track of it!
An approach like this results in an extra 0(n) space being allocated.

The code for this approach would look like the following:
```Python
def list_nth_last(linked_list, n):
	linked_list_as_list = []
	current_node = linked_list.head_node
	while current_node:
		linked_list_as_list.append(current_node)
		current_node = current_node.get_next_node()
	return linked_list_as_list[len(linked_list_as_list) - n]
```

Instead of creating an entire parallel list, we can solve this problem by using two pointers as different positions in the list bur moving at the same rate. As in the previous example, we will use one pointer to iterate through the entire list, but we'll also move a second pointer delayed n steps behind the first one. A count variable ca keep track of the position of the current element in the linked list that the tail pointer is pointing to, which is initially set to 1 which is the first element's position.
The pseudocode for this approach would look like the following:

```
nth last pointer = None
tail pointer = linked list head
count = 1


while tail pointer exists 
	move tail pointer forward
	increment count

	if count >= n+1
		if nth last pointer is None
			set nth last pointer to head
		else
			move nth last pointer forward

return nth last pointer

```

When the tail pointer moves `n` nodes into the linked list from its starting position of 1, it will be at position `n+1`. We want the nth last pointer to be `n` nodes behind, so we set the nth last pointer to the head node at position 1. This is because the position n nodes behind the `n+1`th node is `(n+1) - (n) = 1`. Then, each following iteration will move both pointers at the same speed, until the tail pointer points to the end of the linked list.

Let's visualize the steps of the algorithm through the following example, where we want to obtain the 2nd to last node of the linked list. `T` represents the tail pointer and `N` represents the nth last pointer. For each iteration of the while loop, we will also keep track of the `count` value.

Starting State
```
count = 1
T

1 2 3 4 5
```

First Tick
```
count  = 2
  T
  
1 2 3 4 5
```

Second Tick
```
count = 3
    T
N
1 2 3 4 5
```

Third Tick
```
cout = 4
      T
  N
1 2 3 4 5
```

Fourth Tick
```
count = 5
        T
    N
1 2 3 4 5
```

Final Tick
```
count = 6
          T
      N
1 2 3 4 5 None
```

## Implementation

