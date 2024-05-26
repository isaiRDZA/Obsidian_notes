![[Normlization]]
Given some intermediate value in NN
$$\begin{align}
\mu = \frac{1}{m}\sum z^{i}
\\\sigma^{2} = \frac{1}{m}\sum_{i}(z^{(i)}-\mu)^{2}
\\z^{(i)}_{norm} = \frac{z^{(i)}-\mu}{\sqrt{\sigma^{2}+\epsilon}}
\\ \tilde{z}^{(i)} = \gamma z_{norm}^{(i)} + \beta
\end{align}$$
Where $\gamma$ and $\beta$ are trainable parameters