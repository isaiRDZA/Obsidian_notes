When we are performing a linear regression, sometimes the features we have are very different in scale, for example, if we need to predict the price of a house based on the features: number of bathrooms and size of the construction ($m^{2}$). In this case the size is going to be maybe fifty or one hundred bigger than the number of bathrooms. So the parameters $w_1$ and $w_2$ will have a wide difference. 
The condition described above makes the process of training harder, when the gradient descent algorithm tries to minimize the cost function, the function looks like this:

![[Pasted image 20250203131758.png]]
Forcing the iteration on the algorithm to bounce over the parameter associated with the greater scale. And converging slower.

The difference with a feature scaling:
![[Pasted image 20250203132015.png]]
Here the path to the minimum value over the cost function is straight forward.

The two most practical techniques used in Machine Learning in order to scale the features are:
- [[Min-Max Normalization]]
- [[Standard Normalization]]
