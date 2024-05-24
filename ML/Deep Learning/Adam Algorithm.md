Adam algorithm to compute the gradient descent use the power of the two algorithms [[Gradient descent with momentum]] and ![[RMSProp]]
The algorithm start with
$$\begin{align}V_{dw} = 0,\ S_{dw} = 0,\ v_{db} = 0,\ S_{db} = 0\end{align}$$
`On interatio t:`
	`Compute dW, db using current mini-batch`
	$$\begin{align}V_{dw} = \beta_{1}v_{dw}+(1-\beta_{1})dW,\ v_{db} = \beta_{1}v_{vb}+(1-\beta_{1})db
	\\ s_{dw} = \beta_{2}s_{dw} + (1-\beta_{2})dw^{2},\ s_{db} = \beta_{2}s_{db}+(1-\beta_{2})db^{2}
	\\ V^{corrected}_{dw}= s_{dw} = \frac{V_{dw}}{(1-\beta_{1}^{t})},\ V^{corrected}_{db}= s_{db} = \frac{V_{db}}{(1-\beta_{1}^{t})}
	\\S^{corrected}_{dw}=\frac{s_{dw}}{1-\beta_{2}^{t}},\ S^{corrected}_{db} = =\frac{s_{db}}{1-\beta_{2}^{t}} \\W = W-\alpha\frac{V^{corrected}_{dw}}{\sqrt{s^{corrected}_{dw}+\epsilon}}, \ b=b-\alpha\frac{V^{corrected}_{db}}{\sqrt{s^{corrected}_{db}+\epsilon}}
	\end{align}$$

### Hyperparameters choice
$\alpha$: needs to be tune
$\beta_{1}$:0.9 (du)<-gradient with momentum
$\beta_{2}$:0.999 <- RMS prop
$\epsilon$:$10^{-8}$
Adam stands for Adaptative moment estimation 