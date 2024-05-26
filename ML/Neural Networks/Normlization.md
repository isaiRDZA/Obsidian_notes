
**Subtract the mean**
$$\begin{align}\mu = \frac{1}{m}\sum^{m}_{i=1}x^{(i)}
\\ x:=x-\mu\end{align}$$
**Normalize variance**
$$\sigma^{2} = \frac{1}{m}\sum^{m}_{i=}x^{(i)2}$$

Where sigma is a vector with the variance of each of the features $$x = \frac{x}{\sigma}$$
Use the same $\mu$ and $\sigma$ to normalize the training set an test set

For a training set $x= \begin{bmatrix}x_1\\x_2\end{bmatrix}$
![[Pasted image 20240511181735.png]]

After we substract the mean, we center the data around 0
![[Pasted image 20240511181819.png]]

And in the previous graph we can see that the variance of the input feature $x_1$ is larger than the variance from the feature vector $x_2$. 
To solve this we **normalize the variance**
![[Pasted image 20240511182109.png]]


## Why we normalize input?
Normalizing we modify the cost function allowing the gradient descent algorithm to define a larger $\alpha$ (learning rate). Because we are minimizing a curve very much unifrom than the cost function with not normalizing inputs.
![[Pasted image 20240511182637.png]]

