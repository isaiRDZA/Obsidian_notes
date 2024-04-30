When we want to perform a vector multiplication in code, we usually do:
$$\begin{align} u = \matrix{A}\vec{v}\\u_{i} = \sum_{j}\matrix{A_{i.j}}\vec{v}_{j}\end{align}$$


```Python
u = np.zeros((n,1))
for i in rage(A.shape[0]):
	for i in rage(A.shape[1]):
		u[i] += A[i][j]*v[i]
```

In order to vectorize this previous code, we will use
```Python
u = np.dot(A,v)
```

Say we need to apply the exponential operation on every element of a matrix/vector.
$$v = \begin{bmatrix}v_{1}\\\vdots\\v_{n}\end{bmatrix} \rightarrow  u = \begin{bmatrix}e^{v_1}\\\vdots\\e^{v_{n}}\end{bmatrix}$$

