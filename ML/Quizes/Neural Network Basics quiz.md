Quiz from the week 2 of Deep Learning Specialization

1. In logistic regression given $\vec{x}$ and parameters $w \in \mathbb{R}^{n_{x}}$, $b$ $\mathbb{R}$. Which of the following best expresses what we want $\hat{y}$ to tel us?
- [ ] $\sigma (\matrix{W} \vec{x})$
- [ ] $P(y = \hat{y}|\vec{x})$
- [ ] $P(y=1|\vec{x})$
- [ ] $\sigma(\matrix{W}\vec{x}+b)$

2. Suppose that $\hat{y} = 0.5$ and $y = 0$. What is the value of the "Logistic Loss"? Choose the best option.
- [ ] $+\infty$  
- [ ] $\mathscr{L}(\hat{y},y) = -(y\ log\ \hat{y} + (1-y)log(1-\hat{y}))$ 
- [ ] 0.693
- [ ] 0.5

3. Supose x is a (8,1) array. Which of the following is a valid reshape?
- [ ] `x.reshape(2, 4, 4)`
- [ ] `x.reshape(1, 4, 3)`
- [x] `x.reshape(2, 2, 2)`
- [ ] `x.reshape(-1, 3)`

4. Consider the following random arrays $a$ and $b$, and $c$:
```Python
a = np.random.randn(3,3) #a.shape = (3,3)
b = np.random.randn(2,1) #b.shape = (2,1)
c = a + b
```
What will be the shape of c?
- [x] The computation cannot happen because it is not possible to broadcast more than one dimension.
- [ ] c.shape = (2, 3, 3)
- [ ] c.shape = (3, 3)
- [ ] c.shape = (2, 1)

5. Consider the two following random arrays $a$ and $b$
```Python
a = np.random.randn(1,3) #a.shape = (3,3)
b = np.random.randn(3,3) #b.shape = (2,1)
c = a * b
```
What will be the shape of c?

- [ ] c.shape = (3,3)
- [ ] The computation cannot happen because it is not possible to broadcast more than one dimension.
- [ ] c.shape = (1, 3)
- [ ] The computation cannot happen because the sizes don´t match.

6. Suppose you have $n_x$ input features per example. Recall that $\matrix{X} = \begin{bmatrix}x^{(1)}&x^{(2)}& \dots &x^{(m)}\end{bmatrix}$. What is the dimension of $\matrix{X}$
- [ ] (m,1)
- [ ] $(m, n_{x})$
- [ ] (1,m)
- [ ] $(n_{x}, m)$

7. Consider the following array:
$a = np.array([[2,1],[1,3]])$
what is the result of a * a?
- [ ] $\begin{pmatrix}5&5\\5&10\end{pmatrix}$
- [ ] The computation cannot happen because the sizes don't match. It's going to be an "Error"
- [ ] $\begin{pmatrix}4&2\\2&6\end{pmatrix}$
- [ ] $\begin{pmatrix}4&1\\1&9\end{pmatrix}$

8. Consider the following code snippet:
```Python
a.shape = (3,4)
b.shape = (4,1)

for i in range(3):
	for i in range(4):
		c[i][j] = a[i][j]*b[j]
```
How do you vectorize this?
- [ ] `c = a.T * b`
- [ ] `c = a*b`
- [ ] `c = a*b.T`
- [ ] `c = np.dot(a,b)`

9. Consider the code snippet:
```Python
a.shape = (3,3)
b.shape = (3,3)
c = a**2 +b.T**2
```
Which of the following gives an equivalent output for c?
- [ ] ```for i in range(3):
	c[i] = a[i]**2 +b[i][j]**2```

- [ ] The computation cannot happen because the sizes don't match. It's going to be an "Error"!
- [ ] ```for i in range(3):
		for j in range(3):
			c[i][j] = a[i][j]**2 + b[i][j]**2```
- [ ]  ```for i in range(3):
		for j in range(3):
			c[i][j] = a[i][j]**2 + b[j][i]**2

10. Consider the following computational graph.
![[Pasted image 20240430214804.png]]
What is the output of J?
- [ ] $(a+c)(b-1)$
- [ ] $(c-1)(a+c)$
- [ ] $ab+bc+ac$
- [ ] $(a-1)(b+c)$
