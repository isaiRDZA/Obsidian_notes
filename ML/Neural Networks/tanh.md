Hyperbolic tangent fucntion
$$
\frac{e^{z}-e^{-z}}{e^{z}+e^{-z}}
$$
![[Pasted image 20240504142843.png]]
In hidden units, it always works better than the sigmoid function, because have a 0 mean and you center the data around 0.

A downside of the tanh and the [[Sigmoid]] function is that if $z$ is very large or very small, the derivative of any of these two functions becomes very small (near to zero). This causes the gradient descent algorithm to slow. 
To solve this problem the [[ReLU]] function was introduced.