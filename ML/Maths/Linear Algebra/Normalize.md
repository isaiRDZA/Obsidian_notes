Normalizing rows is a common rechinique we use in Machine Learning and Deep Learning. I ofte leads to a better performance because gradient descent converges gaster after normalization. Here, by normalization we mean changing x to $\frac{x}{||x||}$ (dividing each row vector of x by its norm).
For example, if
$$ x = \begin{bmatrix}
						10&3&4\\
						2&6&4
		\end{bmatrix}				
						$$

