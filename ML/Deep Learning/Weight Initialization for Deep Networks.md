![[Weight Initialization]]

When we are calculating $z$ the longer the features we have, the smaller the weights should be, because:
$$z = w_1x_1 + w_1x_2 + w_1x_3 + ... + w_nx_n + b$$
So the gradient descent become slower. The problem of [[Vanishing Gradients]] and [[Exploding gradients]].
To solve this we should initialize the parameters $W$ as follows:
`Wl = np.random.randn(W.shape)*np.sqrt(1/n**(l-1))`
## weight initialization for ReLU
$$\frac{2}{n}$$
`Wl = np.random.randn(W.shape)*np.sqrt(2/n^(1-l))`
function
## Xavier initialization (tanh)
$$\sqrt{\frac{1}{n^{[l-1]}}}$$
#hyperparameters
