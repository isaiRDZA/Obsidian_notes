Regularization is one of the most widely used methods to address the problem of over-fitting.
To regularize the cost function of the logistic regression we add the regularization term to the cost function like below.
$$\begin{align}J(w,b) = \frac{1}{m}\sum^{m}_{i = 1} \mathscr{L} (\hat{y}^{(i)}, y^{(i)}) + \frac{\lambda}{2m}||w||_{2}^{2}
\end{align}$$
Normally the regularization for parameter be is not used.
$$+\frac{\lambda}{2m}b^{2}$$


### L2 regularization (weight decay)
$$\begin{align}
\\ ||w||^{2}_{2} = \sum^{n_{x}}_{j=1} w^{2}_{j} = w^{T}w
\end{align}$$
## Neural Network regularization
$$\begin{align}J(w^{[1]}, b^{[1]},..., w^{[L]}, b^{[L]}) = \frac{1}{m} \sum_{i=1}^{n}\mathscr{L}(\hat{y}, y^{(i)}) + \frac{\lambda}{2m}\sum^{L}_{l=1}||w^{[l]}||^{2}_{F}
\\
\end{align}$$
where $\matrix{W}: (n^{l}, n^{[l-1]})$

Frobenius norm of a matrix
$$||w^{[l]}||_{F}^{2} = \sum_{i=1}^{n^{[l]}} \sum_{j=1}^{n^{[l-1]}}(w_{i,j}^{[l]})²$$


