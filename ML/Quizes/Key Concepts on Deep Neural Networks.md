1. What is the "cache" used for in our implementation of forward propagation?
- [ ] We use it to pass variables computed during backward propagation to the corresponding forward step. It contains useful values for forward propagation to compute activations.
- [ ] It is used to keep track of the hyperparameters that we are searching over, to speed up computation.
- [ ] We use it to pass $Z$ computed during forward propagation to the corresponding backward propagation step. It contains useful values for backward propagation to compute derivatives.
- [ ] It is used to cache the intermediate values of the cost function during training.

2. During the backpropagation process, we use gradient descent to change the hyperparametes. True/False?
- [ ] False
- [ ] True

3. Considering the intermediate results below, which layers of a deep neural networks are they likely to belong.
 ![[Pasted image 20240515204113.png]]
- [ ] Later layers of the deep neural network.
- [ ] Input layer of the deep neural network.
- [ ] Middle layers of the deep neural network.
- [ ] Early layers of the deep network.

4. Vectorization allows you to compute forward propagation in al $L$-layer neural network without an explicit for-loop (or any other explicit iterative loop) over the layers l = 1, 2, ..., L. True/Flase?
- [ ] True
- [ ] False

5. Assume we store the value for $n^{[l]}$ in an array called llayer_dims, as follows: layer_dims = $[n_{x},4,3,2,1]$. So layer 1 has four hidden units, layer 2 has 3 hidden units and so on. Which of the following for-loops will allow you to initialize the parameters for the model?
- [ ] 
```Python
for i in range(1, len(layer_dims)):
	parameter['W' + str(i)] = np.random.randn(layer_dims[i-1],layer_dims[i])*0.01
	parameter['b' + str(i)] = np.random.randn(layer_dims[i], 1)*0.01
```
- [ ] 
```Python
for i in range(1, len(layer_dims)):
	parameter['W'+ str(i)] = np.random.randn(layer_dims[i], layer_dims[i-1])*0.01
	parameter['b' + str(i)] = np.random.randn(layer_dims[i],1)*0.01
```
- [ ] 
```Python
for i in range(1, len(layer_dims)/2):
	parameter['W'+str(i)] = np.random.randn(layer_dims[i], layer_dims[i-1])*0.01
	parameter['b'+str(i)] = np.random.randn(layer_dims[i],1)*0.01
```
- [ ] 
```Python
for i in range(1, len(layer_dims)/2):
	parameter['W' + str(i)] = np.random.randn(layer_dims[i], layer_dims[i-1])*0.01
	parameter['b' + str(i)] = np.random.randn(layer_dims[i-1],1)*0.01
```

6. Consider the following neural network:
![[Pasted image 20240515235416.png]]
How may layer does this network have?
- [ ] The number of layers L is 6
- [ ] The number of layers L is 5
- [ ] The number of layers L is 4
- [ ] The number of layers L is 2

7. If L is the number of layers of a neural network then $dZ^{[L]} = A^{[L]}-Y$. True/False 
- [ ] True
- [ ] False

8. For anu mathematical funciton you can compute with an L-layered deep neural network with N hidden units there is a shallow neural network that req 