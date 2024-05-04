$\sigma(z) = \frac{1}{1+e^{-z}}$ 

![[Pasted image 20240424220652.png]]
Here if $z$ is large $\sigma(z)$ will be approximate 1
and if $z$ is a large negative number $\sigma(z)$ will be approximate 0

## Derivative
The derivative of the sigmoid function is equal to
$$\begin{align}
\frac{d\sigma}{dx} = \frac{d\sigma}{du}\cdot\frac{du}{dx}
\\ du = 1+e^{-x}
\\\sigma = du^{-1}
\\ \frac{d\sigma}{du}=-1\cdot du^{-2}
\\ = -\frac{1}{(1+e^{-x})^{2}}
\\ \frac{du}{dx} = -e^{-x}
\\ \frac{d\sigma}{dx} = (1+e^{-x})^{-2} \cdot (e^{-x})
\\= \frac{1}{1+e^{-x}}\cdot\frac{e^{-x}+(1-1)}{1+e^{-x}}
\\ = \frac{1}{1+e^{-x}}\cdot(1-\frac{1}{1+e^{-x}})
\\ = \sigma(1-\sigma)
\\= a\cdot(1-a
)
\end{align}$$
