When running gradient descent, if we plot the values it takes on each epoch, we can notice that the value bounce a lot, which makes the algorithm takes more steps to optimize the cost function.
![[Pasted image 20240516181144.png]]

For example in the function from the image we would have a better performance if we just slow the learning in the vertical direction and increase the magnitude on the steps over the horizontal direction.
To achieve this behavior we ca use the equation from exponentially weighted averages. Modifying the backpropagation like as follows:
