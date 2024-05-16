![[Excalidraw/Mini-batch gradient descent|Mini-batch gradient descent]]
When we train a deep learning model with a lot of data. The problem is that the gradient descent algorithm need to finish doing all the matrix calculation all over the network to start the first step in descending the gradient.
To optimize the running time in training a deep neural network is design the mini-batch. This runs steps of gradient descent while we are passing blocks of our training data called mini batches.
So in order to perform mini-batch gradient descent we need to go to the full process of training a deep NN but with a portion of our training data:

`for t = 1, ..., 500{`
	Forward prop on $X^{t}$
		$X^{[1]} = W^{[1]}X^{\{t\}}+b$
		$A^{[1]} = g^{[1]}(Z^{[1]})$
		  $\vdots$
		$A^{[L]} = g^{[L]}(Z^{[L]})$
	Compute cost $J^{\{t\}} = \frac{1}{100}\sum^{l}_{i=1}\mathscr{L}(\hat{y}^{(i)}, y^{(i)}) + \frac{\lambda}{2 \cdot 1000} \sum_{l} ||W^{[l]}||^{2}_{F}$ 
	Backprop to compute gradient cost $J^{\{t\}} (X^{\{t\}}, Y^{\{t\}})$ 
	 $W^{[l]} = W^{[l]}-\alpha dW^{[l]},\ b^{[l]} = b^{[l]}-\alpha db^{[l]}$
	 And all of these will happen for the **1 epoch** pass through the mini batch trainnig set