![[Normlization]]
Given some intermediate value in NN
$$\begin{align}
\mu = \frac{1}{m}\sum z^{i}
\\\sigma^{2} = \frac{1}{m}\sum_{i}(z^{(i)}-\mu)^{2}
\\z^{(i)}_{norm} = \frac{z^{(i)}-\mu}{\sqrt{\sigma^{2}+\epsilon}}
\\ \tilde{z}^{(i)} = \gamma z_{norm}^{(i)} + \beta
\end{align}$$
Where $\gamma$ and $\beta$ are trainable parameters

## Why batch normalization works?
At the intermediate layers the neurons experience a covariate shift as the intermediate layers are always receiving changing inputs from its previous-layer neurons.

![[Pasted image 20240526175958.png]]