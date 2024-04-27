You can think of softmax as a normalization function used when your algorithm needs to classify two or more classes.

Instructions:
- For $x \in \mathbb{R}^{1Xn}$,
$$ \begin{align}softmax(x) = softmax (\begin{bmatrix}x_1 & x_2 & ... & x_n\end{bmatrix})\\
= \begin{bmatrix} \frac{e^{x}_{1}}{\sum_{j}e^{x_{j}}}&\frac{e^{x}_{2}}{\sum_{j}e^{x_{j}}}&...&\frac{e^{x}_{n}}{\sum_{j}e^{x_{j}}}  \end{bmatrix} \end{align}$$
