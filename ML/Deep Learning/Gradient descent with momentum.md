When running gradient descent, if we plot the values it takes on each epoch, we can notice that the value bounce a lot, which makes the algorithm takes more steps to optimize the cost function.
![[Pasted image 20240516181144.png]]

For example in the function from the image we would have a better performance if we just slow the learning in the vertical direction and increase the magnitude on the steps over the horizontal direction.
To achieve this behavior we ca use the equation from exponentially weighted averages. Modifying the backpropagation like as follows:
```
Momentum:
On iteration t:
	Compute dW, db on current mini-batch
	Vdw = beta*Vdw + (1-beta)dW
	Vdb = beta*Vdb + (1-beta)db
	W = W - alpha*Vdw, b = b - alpa * Vdb
```
We could make an analogy to `dW` and `db` to be the acceleration of a particle moving in a bowl towards the bottom. `Vdw` and `Vdb` to be the velocity and `beta` to be the friction.

For this implementation **the hyperparameters are $\alpha$ and $\beta$**.

