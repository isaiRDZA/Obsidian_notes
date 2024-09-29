We have three notation to cathegorize an algorithm:
## Big O
Used to described the worst case time execution for a particular input N to the algorithm we want to evaluate.

## Big $\theta$ 
Used to describe the exact time execution for a given algorithm

## Big $\Omega$
Used to describe the best case in time execution for a given algorithm.


## Example

Given a list of integers with **N** objects, we must find the asymptotic notation for an algorithm that needs to search through the list and find the integer equals to 3.
#### Big $\Omega$ will be $\Omega (1)$:
The best case for an algorithm like this is when the first element in the list is the value we are looking for, in this case the algorithm will only need to execute one time.
#### Big O will be 0(N):
This is the worst case when the number is at the very end of the input list, in this case, the agorithm needs to traverse thorugh the whole list to find the number,



![[Pasted image 20240920112713.png]]
