1. Which notation would you use to denote the 3rd layer's activations when the input is the 7th example from the 8th minibatch?
- [ ] $a^{[3]\{8\}(7)}$
- [ ] $a^{[3]\{7\}(8)}$
- [ ] $a^{[8]\{3\}(7)}$
- [ ] $a^{[8]\{7\}(3)}$

2. Suppose you don't face any memory related problems. Which of the following make more use of vectorization
- [ ] Stochastic Gradient Descent
- [ ] Stochastic Gradient Descent, Batch Gradient Descent, and Mini-Batch Gradient Descent all make equal use of vectorization
- [ ] Batch Gradient Descent
- [ ] Mini-Batch Gradient Descent with mini-batch size $\frac{m}{2}$

3. Which of the following is true about batch gradient descent?
- [ ] It has many mini-batches as examples in the training set
- [ ] It is the same as stochastic gradient descent, but we don't use random elements.
- [ ] It is the same as the mini-batch gradient descent when the mini-batch size is the same as the size of the training set.

4. While using mini-batch gradient descent with a batch size larger than 1 bur less than m. the plot of the cost function J looks like this:
![[Pasted image 20240516171657.png]]
You notice that the value of J is not always decreasing. Which of the following is the most likely reason for that?
- [ ] You are not implementing the moving averages correctly. Using moving averages will smooth the graph.
- [ ] The algorithm is on local minimum this the noisy behaviour.
- [ ] In mini-batch gradient descent we calculate $J(\hat{y}^{\{t\}}, y^{\{y\}})$ thus with wach batch we compute over a new set of data.
- [ ] A  bad implementation of the backpropagation process, we should use gradient check to debug our implementation.

5. Suppose the temperature in Casablanca over the first two days of January are the sa