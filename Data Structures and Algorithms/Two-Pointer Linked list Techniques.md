Learn how to approach Linked List problems with multiple iterator pointers.

Many common singly linked list problems can be solved by iterating with two pointers. This is sometimes know as the runner technique.

# Two pointers Moving in Parallel

Consider the following two problems:
Create a method that returns the nth last element of singly linked list.
For example: given a linked list with the following elements 1 -> 2 -> 3 -> 4 -> 5, return the 2nd to last element. Then answer would be element 4.
In order to do this, you'll need some way of knowing how far you are from the end of the list itself. However, in a singly linked list, there's no easy way to iterate back through the list when y