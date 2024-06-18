For [[Deep Learning]] convolution is an operation that consist in multiplying a matrix with a smaller matrix called kernel or filter.
The algorithm follows the next instructions:
1. Start over the top left component of the input matrix.
2. Multiply each component for its corresponding number on the kernell.
3. Sum the multiplication and place the result on the first component of the output matrix (1,1)
4. Step a '[[Stride]]' to the right and then down to the bottom at each step.
5. Start then over (1, 1+stride )
![[Pasted image 20240617205414.png]]
