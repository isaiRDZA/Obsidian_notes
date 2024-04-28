For logistic regression the [[Activation functions]] that we use is the [[Sigmoid]] 
Given $x$, want $\hat{y} = P(y=1|x)$
where $y = \sigma(\omega^{T}x+b)$
and we substitute $z = \omega^{T}x+b$ 

## Cost function
Given ${\{(x^{(1)},y^{(1)} ), ..., (x^{(m)}, y^{(m)})\}}$ want $\hat{y}^{(i)} \approx y^{(i)}$ 
then the loss (error) function could be: $\mathscr{L}(\hat{y}, y) = -(ylog(\hat{y})+ (1-y)log(1-\hat{y})$  
Then the **the [[Cost function]]**: $J(w,b) = \frac{1}{m}\sum_{i = 1}^{m}\mathscr{L}(\hat{y}^{(i)}, y^{(i)})$ 

**What is the difference between the cost function and the loss function for logistic regression?**
*The loss function computes the error for a single training example; the cost function is the average of the loss functions of the entire training set.*

## Derivative with Computation Graph  (Gradi)