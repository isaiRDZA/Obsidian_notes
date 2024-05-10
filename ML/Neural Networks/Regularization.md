Regularization is one of the most widely used methods to address the problem of over-fitting.
To regularize the cost function of the logistic regression we add the regularization term to the cost function like below.
$$\begin{align}J(w,b) = \frac{1}{m}\sum^{m}_{i = 1} \mathscr{L} (\hat{y}^{(i)}, y^{(i)}) + \frac{\lambda}{2m}||w||_{2}^{2}
\end{align}$$
Normally the regularization for parameter be is not used.
$$+\frac{\lambda}{2m}b^{2}$$
## L1 regularization
$$\frac{\lambda}{m}\sum^{n_x}_{i = 1}|w| = \frac{\lambda}{m}||w||$$

### L2 regularization (weight decay)
$$\begin{align}
\\ ||w||^{2}_{2} = \sum^{n_{x}}_{j=1} w^{2}_{j} = w^{T}w
\end{align}$$
## [[neural network]] regularization
$$\begin{align}J(w^{[1]}, b^{[1]},..., w^{[L]}, b^{[L]}) = \frac{1}{m} \sum_{i=1}^{n}\mathscr{L}(\hat{y}, y^{(i)}) + \frac{\lambda}{2m}\sum^{L}_{l=1}||w^{[l]}||^{2}_{F}
\\
\end{align}$$
where the size of $\matrix{W}: (n^{l}, n^{[l-1]})$

For this regularization we are not using the usual norm we are using **Frobenius norm** of a matrix
$$||w^{[l]}||_{F}^{2} = \sum_{i=1}^{n^{[l]}} \sum_{j=1}^{n^{[l-1]}}(w_{i,j}^{[l]})²$$
## [[Gradient Descent]] with normalization
For backpropagation we have
$$\begin{align}dw^{[l]} = backprop + \frac{\lambda}{m}w^{[l]}
\\
\frac{\partial J}{\partial w^{l}} = dw^{[l]}
\\
w^{[l]} = w^{[l]}-\alpha  dw^{[l]}
\\w^{[l]} = w^{[l]}- \alpha[(backprop)+\frac{\lambda}{m}w^{[l]}]
\\= w^{[l]}-\frac{\alpha\lambda}{m}w^{[l]}-\alpha(backprop)
\\ = w^{[l]}(1-\frac{\alpha\lambda}{m})-\alpha(backprop)
\end{align}$$
This is why L2 normalization is also called **weight decay**.

## How does regularization reduces overfiting
- When we choose a larger $\lambda$ we are forcing the W values to reduce close to zero, so it is like if we were disconnecting neurons or nullifying some of them. 
- When we add the regularization parameter $w^{[l]}= w^{[l]}(1-\frac{\alpha\lambda}{m})-\alpha(backprop)$ we are also affecting $z^{[l]} = W^{[l]}a^{[l-1]} +b$, if W is smaller, then, $z^{[l]}$ is also smaller. And for example, when working for tanh, reducing z is make sure that we will be in the almost linear part:
![[Pasted image 20240510172556.png]]
This prevent the overall layer to overfit the training set. Because the output will have a more linear behaviour.
