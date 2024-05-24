RMS is just like gradient descent with momentum but adding a square to the parameter $dW$ and $db$.
When we had the following for momentum:
![[Gradient descent with momentum]]

We have:
`On iteration t:`
	`Compare dW, db on current mini-batch`
	$$\begin{align}S_{dw} = \beta S_{dw} + (1-\beta)dW^{2}
	\\S_{db} = \beta S_{db}+(1-\beta)db^{2}
	\\ W = w-\alpha \frac{dW}{\sqrt{S_{dw}}+\epsilon}\ \ ,\ b = b-\alpha\frac{db}{\sqrt{s_{db}+\epsilon}}\end{align}$$
