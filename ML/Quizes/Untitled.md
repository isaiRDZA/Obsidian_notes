1.  Suppose a neural network contains a dense layer that connects one hidden layer $h$, with $n_{i}$ units to a following hidden layer $n_{i+1}$ units. How many parameters are needed for this connection?
- [ ] $n_{i}, n_{i+1}$
- [x] $(n_{i}+1)n_{i+1}$
- [ ] $n_{i}$
- [ ] $n_{i}+n_{i+1}$


2. Why do we use non-linear activation functions (such as tanhtanh or relurelu) in neural networks?
- [ ] Without non-linear activation functions, the network would only be able to model linear functions of the data.
- [ ] To induce sparse connectivity in the network weights.
- [ ] So that the model activations are equivariant with respect to the input features
- [ ] To allow the usage of higher learning rates, thus speeding up the convergence during the optimization.
3. How many trainable parameters does a feedforward network have with input shape `(64,)`, three hidden layers with 16 units each and a final linear layer with 8 units?
- [ ]  1720
- [ ] 1448
- [ ] 952
- [ ] 1856
