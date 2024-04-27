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


Note that you can divide matrices of different sizes and it works fine: this is called [[broadcasting]].
With `keepdims = True`the result will broadcast correctly against the original x.
`axis = 1` means you are going to get the norm in a row-wise manner. If you need the norm in a column-wise way, you would need to set axis = 0.
`numpy.linalg.norm` has another parameter `ord` where we specify the type of normalization to be done.


## Example:
Implement normalizeRows() to normalize the rows of a matrix. After applying this function to an input matrix x, each row of x should be a vector of unit lenght (meaning length 1).

```Python
def normalize_rows(x):
	"""
	Implement a function that normalizes each row of the matrix x (to have unit lenght).
	Argument:
	X -- A numpy matrix of shape (n, m)
	Returns:
	X -- The normalized (by row) numpy matrix. You are allowed to modify x.
	"""
	x_norm = np.linalg.norm(x, axis = 1, keepdims = 1, ord = 2)
```

```Python
x = np.array([[0., 3., 4.],
              [1., 6., 4.]])
print("normalizeRows(x) = " + str(normalize_rows(x)))
```
![[Pasted image 20240427001501.png]]

