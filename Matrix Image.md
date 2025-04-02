The image of a matrix, also called **column space**, is the set of all possible linear combinations of its column vectors. It represents the **range** of the corresponding linear transformation.

For  $\Phi :\ V \rightarrow W$, It is define as:
$Im(\Phi)\:=\Phi (V)= \{ \textbf{w}\in W  |\ \exists \ \textbf{v} \in V : \ \Phi (v) = \textbf{w}\}$ 


If $A$ is an $m \times n$ matrix, its image ([[column space]]) is:

$$Im(A) = \{Ax\ | \ x \in \mathbb{R}^{n} \}$$ Alternatively, it can be defined as:
$$Im(A) = span(a_{1}, a_{2}, ... ,a_{n})$$
where $a_{i}$ are column vectors of $A$.

## Properties

- Dimension: The dimension of the image of $A$ is called the [[Rank]] of A, denoted as $rank(A)$.
- Full column rank: If $rank(A) = n$ (number of columns), then the columns of $A$ form a [[Vector Base]] of $\mathbb{R}^{m}$.
## Example
Let
$$A = \begin{bmatrix}
						1&2\\
						3&6\\
						5&10
		\end{bmatrix}	$$
The column vectors are

$$\bf{a_{1}} = \begin{bmatrix}
						1\\
						3\\
						5
		\end{bmatrix},\ \ \ \ \ \bf{a_{2}} =	\begin{bmatrix}
						2\\
						6\\
						10
		\end{bmatrix},$$
Since $\bf{a_{2}} = 2a_{1}$, the two columns are linearly dependent. This, the image A is **one-dimensional** and spanned by $\bf{a_{1}}$:
$$Im(A) = span \left\{ \begin{bmatrix}
						1\\
						3\\
						5
		\end{bmatrix} \right\}	$$



