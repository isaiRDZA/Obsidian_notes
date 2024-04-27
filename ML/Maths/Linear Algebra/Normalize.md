Normalizing rows is a common rechinique we use in Machine Learning and Deep Learning. I ofte leads to a better performance because gradient descent converges gaster after normalization. Here, by normalization we mean changing x to $\frac{x}{||x||}$ (dividing each row vector of x by its norm).
For example, if
$$ x = \begin{bmatrix}
						0&3&4\\
						2&6&4
		\end{bmatrix}				
						$$

then

$||x||$ = 
```Python 
np.linalg.norm(x, axis =1, keepdims = True)
```
= $$\begin{bmatrix}5\\\sqrt{56}\end{bmatrix}$$
and 
$$
x\_normalized = \frac{x}{||x||} = \begin{bmatrix} 0&\frac{3}{5}&\frac{4}{5}\\
\frac{2}{\sqrt{56}}&\frac{6}{\sqrt{56}}&\frac{4}{\sqrt{56}}\end{bmatrix}
$$


Note that you can divide matrices of different sizes and it works fine: this is called broadcasting 
