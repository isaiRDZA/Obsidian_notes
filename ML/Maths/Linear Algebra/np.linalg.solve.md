[[Numpy]] linear algebra package provides quick and reliable way to solve system of linear equations using function np.linalg.solve(A, b). Here $A$ is a matrix, each row of which represents one equation in the system and each column corresponds to tha variable $x_{1}$, $x_{2}$. And b is a 1-D array of the free (right side) coefficients.
[Documentation]([numpy.linalg.solve — NumPy v1.26 Manual](https://numpy.org/doc/stable/reference/generated/numpy.linalg.solve.html)) 

Given the system of linear equations
$$\begin{cases}
-x_1+3x_2 = 7\\
3x_1+2x_2=1
\end{cases}$$
You can set a matrix $A$ and 1-D array $b$ as:
```Python
A = np.array([
			  [-1, 3],
			  [3,2]
], dtype = np.dtype(float))
b = np.array([7, 1], dtype = np.dtype(float))

x = np.linalg.solve(A, b)
```

