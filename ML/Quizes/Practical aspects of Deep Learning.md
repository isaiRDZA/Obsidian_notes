1. If you hace 20,000,000 examples, how would you split the train/dev/test set?
- [ ] 99% train. 0.5% dev. 0.5% test
- [ ] 60% train. 20% dev. 20% test
- [ ] 90% train. 5% dev. 5% test

2. The dev and test set should
- [ ] Come from the same distribution
- [ ] Have the same number of examples
- [ ] Come from different distributions
- [ ] Be identical to each other (same(x, y) pairs)

3. A model developed for a project is presenting high bias. One of the sponsors of the project offers some resources that might help reduce the bias. Which of the following additional resources has a better chance to help reduce the bias?
- [ ] Gather more data for the project
- [ ] Give access to more computational resources like GPUs
- [ ] Use different sources to gather data and better test the model

4. You are working on an automated check-out kiosk for a supermarket, and are building a classifier for apples, bananas and oranges. Suppose your classifier obtains a training set error of 0.5%, and dev set error of 7%. Which of the following are promising things to try to improve your classifier?
- [ ] Increase the regularization parameter lambda
- [ ] Decrease the regularization parameter lambda
- [ ] Get more training data
- [ ] Use a bigger neural network

5. Which of the following are regularization techniques
- [ ] Dropout
- [ ] Increase the number of layers on the network
- [ ] Weight decay
- [ ] Gradient Checking

6. Tor reduce high variance, the regularization hyperparameter lambda must be increased. True/False?
- [ ] True
- [ ] False

7. Which of the following are true about dropout?
- [ ] In practice. it eliminates units of each layer with a probability of keep_prob
- [ ] It helps to reduce overfitting
- [ ] It helps to reduce the bias of amodel.
- [ ] In practice, it eliminates units of each layer with a probability of 1-keep_prob

8. During training a deep neural network that uses the tanh activation function, the value of the gradients is practically zero. Which of the following is most likely to help the vanishing gradient problem?
- [ ] Increase the number of layers of the network
- [ ] Use larger regularization parameter.
- [ ] Increase the number of cycles during the training
- [ ] Use Xavier initialization

9. Which of the following actions increase the regularization of a model?
- [ ] Decrease the value keep_prob in dropout
- [ ] Use Xavier initialization
- [ ] Increase the value of keep_prob in dropout

10. Which of the following is the correct expression to normalize the input x?
- [ ] $x = \frac{x}{\sigma}$
- [ ] $x = \frac{1}{m} \sum^{m}_{i=1}x^{(i)}$
- [ ] $x = \frac{x-\mu}{\sigma}$
- [ ] $x = \frac{1}{m}\sum_{i=1}^{m}(x^{(i)})^{2}$

11. With the inverted dropout technique, at test time:
- [ ] You do not apply dropout (do not randomly eliminate units), but keep the 1/keep_prob factor in the calculations used in training
- [ ] You do not apply dropout (do not randomly eliminate units) and do not keep the 1/keep_prob factor in the calculations used in training
- [ ] You apply dropout(randomly eliminating units) but keep the 1/keep_prob factor in the calculations used in training
- [ ] You apply dropout (randomly eliminating units) and not keep the 1/keep_prob factor in the calculations used in training