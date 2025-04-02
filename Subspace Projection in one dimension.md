$$
\begin{align}
& \pi_{U}(x) = \lambda \bf{b}, \lambda \in \mathbb{R}\\
& \langle\ \pi_{U}(x)-\bf{x}, \bf{b} \rangle = 0\\
& \lambda = \frac{\bf{b}^{\top}\bf{x}}{\left\Vert \bf{b} \right\Vert^{2}} \\
&\pi_{U}(x) = \lambda\bf{b} = \bf{b}\lambda = \frac{\bf{b}\bf{b}^{\top}}{\left\Vert \bf{b} \right\Vert^{2}}\bf{x}\\
&=\bf{P}_{\pi}(\bf{x})\\
&\bf{P}_{\pi} = \frac{\bf{b}\bf{b}^{\top}}{\left\Vert \bf{b} \right\Vert^{2}}
\end{align}
$$
![[Pasted image 20250325110427.png]]
Where:
- $P_{\pi}$ is the projection matrix
- $\lambda$ is the value of the vector $\bf{x}$ projected over the vector $\bf{b}$
-  $\langle\ \pi_{U}(x)-\bf{x}, \bf{b} \rangle = 0$ is the orthogonal vector between $\bf{b}$ and $\bf{x}$.