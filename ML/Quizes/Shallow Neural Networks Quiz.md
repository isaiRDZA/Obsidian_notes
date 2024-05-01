1. Which of the following are true?
- [ ] $w_{3}^{[4]}$ is the column vector of parameters of the third layer and fourth neuron.
- [ ] $w_{3}^{[4]}$ is the row vector of parameters of the fourth layer and third neuron.
- [ ] $a^{[3](2)}$ denotes the activation vector of the second layer for the third example.
- [ ] $w_{3}^{[4]}$ is the column vector of parameters of the fourth layer and third neuron.
- [ ] $a^{[2]}$ denotes the activation vector of the second layer.
- [ ] $a_{3}^{[2]}$ denotes the activation vector of the second layer for the third example

2. In which of the following cases is the linear (identity) activation function most likely used?
- [ ] As activation function in the hidden layers.
- [ ] For binary classification problems.
- [ ] The linear activation is never used.

3. Which of the following is the correct vectorized implementation of forward propagation for layer 2?
- [ ] $\begin{align}Z^{[2]} = \matrix{W}^{[2]} \matrix{X} + b^{[2]}\\A^{[2]} = g^{[2]}(\matrix{Z^{[2]}})\end{align}$
- [ ] $\begin{align}Z^{[2]} = \matrix{W}^{[2]} \matrix{A}^{[1]} + b^{[2]}\\A^{[2]} = g^{[2]}(\matrix{Z^{[2]}})\end{align}$
- [ ] $\begin{align}Z^{[1]} = \matrix{W}^{[1]} \matrix{X} + b^{[1]}\\A^{[1]} = g^{[1]}(\matrix{Z^{[1]}})\end{align}$
- [ ] $\begin{align}Z^{[2]} = \matrix{W}^{[2]} \matrix{A}^{[1]} + b^{[2]}\\A^{[2]} = g(\matrix{Z^{[2]}})\end{align}$

4. You are building a binary classifier for recognizing cucumbers (y = 1) vs watermelons (y = 0). Which one of these activation functions would you recommend using for the output layer?
- [ ] Sigmoid
- [ ] Leaky ReLU
- [ ] tanh
- [ ] ReLU

5. Consider the following code
```Python
x = np.random.rand(4,5)
y = np.sum(x, axis = 1)
```
What would be the y.shape?
- [ ] (4,)
- [ ] (5,)
- [ ] (1,5)
- [ ] (4,1)

6. Suppose you have built a neural network with one hidden layer and tanh as activation function for the hidden layers. Which of the following is a best option to initialize the weights?
- [ ] Initialize all weight to 0.
- [ ] Initialize the weights to small random numbers.
- [ ] Initialize all weights to a single number chosen randomly.
- [ ] Initialize the weights to large random numbers.

7. A single output and single layer neural network that uses the sigmoid function as activation is equivalent to the logistic regression. True/False
- [ ] True
- [ ] False

8. Which of the following is true about the ReLU activation functions?
- [ ] They cause several problems in practice because they have no derivative at 0. That is why ReLU Leaky was invented.
- [ ] They are the go option when you don't know what activation function to choose for hidden layers.
- [ ] They are only used in the case of regression problems, such as predicting houses.
- [ ] They are increasingly being replaced by the tanh in most cases.

9. Consider the following 1 hidden layer neural network
![[Pasted image 20240430202149.png]]
- [ ] $b^{[1]}$ will have shape (3,1).
- [ ] $W^{[1]}$ will have shape (4,3).
- [ ] $b^{[2]}$ will have shape (1,1).
- [ ] $W^{[1]}$ will have shape (3,4).
- [ ] $b^{[1]}$ will have shape (1,3).
- [ ] $b^{[2]}$ will have shape (3,1).

10. Consider the following 1 hidden layer neural network
![[Pasted image 20240430203419.png]]
What are the dimensions of $\matrix{Z^{[1]}}$ and $\matrix{A^{[1]}}$? 
- [ ]  $\matrix{Z}^{[1]}$ and $\matrix{A}^{[1]}$ are (3,1)
- [ ] $\matrix{Z}^{[1]}$ and $\matrix{A}^{[1]}$ are (3,m)
- [ ] $\matrix{Z}^{[1]}$ and $\matrix{A}^{[1]}$ are (4,m)
- [ ] $\matrix{Z}^{[1]}$ and $\matrix{A}^{[1]}$ are (4,1)