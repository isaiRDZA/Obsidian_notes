You can think of softmax as a normalization function used when your algorithm needs to classify two or more classes.

Instructions:
- For $x \in \mathbb{R}^{1Xn}$,
$$ \begin{align}softmax(x) = softmax (\begin{bmatrix}x_1 & x_2 & ... & x_n\end{bmatrix})\\
= \begin{bmatrix} \frac{e^{x}_{1}}{\sum_{j}e^{x_{j}}}&\frac{e^{x}_{2}}{\sum_{j}e^{x_{j}}}&...&\frac{e^{x}_{n}}{\sum_{j}e^{x_{j}}}  \end{bmatrix} \end{align}$$
- For a matrix *X*: $\in \mathbb{R}^{mxn}$, $X_{ij}$ maps to the element in the $i^{th}$ row and $j^{th}$ column of x thus we have:
$$\begin{align}softmax(x) = softmax\begin{bmatrix}x_{11} & x_{12} & x_{13} & \dots & x_{1n}\\
x_{21} & x_{22} & x_{23} & \dots & x_{2n}\\
\vdots & \vdots & \vdots & \ddots & \vdots\\
x_{m1} & x_{m2} & x_{m3} & \dots &x_{mn}
\end{bmatrix}\\
= 
\begin{bmatrix}\frac{e^{x}_{11}}{\sum_{j}e^{x_{1j}}} & \frac{e^{x}_{12}}{\sum_{j}e^{x_{1j}}} & \frac{e^{x}_{13}}{\sum_{j}e^{x_{1j}}} & \dots & \frac{e^{x}_{1n}}{\sum_{j}e^{x_{1j}}}\\
\frac{e^{x}_{21}}{\sum_{j}e^{x_{2j}}} & \frac{e^{x}_{22}}{\sum_{j}e^{x_{2j}}} & \frac{e^{x}_{23}}{\sum_{j}e^{x_{2j}}} & \dots & \frac{e^{x}_{2n}}{\sum_{j}e^{x_{2j}}}\\
\vdots & \vdots & \vdots & \ddots & \vdots\\
\frac{e^{x}_{m1}}{\sum_{j}e^{x_{mj}}} & \frac{e^{x}_{m2}}{\sum_{j}e^{x_{mj}}} & \frac{e^{x}_{m3}}{\sum_{j}e^{x_{mj}}} & \dots &\frac{e^{x}_{mn}}{\sum_{j}e^{x_{mj}}}
\end{bmatrix}\\
\\
\begin{bmatrix}
sotmax(first \ row\ of\ x)\\
sotmax(second \ row\ of\ x)\\
\vdots \\
sotmax(last \ row\ of\ x)\\
\end{bmatrix}
\end{align}$$
Each traning example is in its own column of the matrix. Also, each feature will be in its own row (each row has data for the same feature).
Softmax should be performed for all features of each training example, so softmax would be performed on the columns.

For this example the common math notation m x n
where m is the number of rows and n is the number of columns

```Python
def softmax(x):
    """Calculates the softmax for each row of the input x.

    Your code should work for a row vector and also for matrices of shape (m,n).

    Argument:
    x -- A numpy matrix of shape (m,n)

    Returns:
    s -- A numpy matrix equal to the softmax of x, of shape (m,n)
    """
    # YOUR CODE STARTS HERE
    x_exp = np.exp(x)
    x_sum = np.sum(np.exp(x), axis =1, keepdims = True)
    s = x_exp/x_sum
    
    # YOUR CODE ENDS HERE
    
    return s

t_x = np.array([[9, 2, 5, 0, 0],
                [7, 5, 0, 0 ,0]])
print("softmax(x) = " + str(softmax(t_x)))

```

![[Pasted image 20240427014213.png]]
If we print `x_sum` we will get a vector $\vec{v} \in \mathbb{R}^{1,2}$ for this example, the sum of each row of our input vector.
```Python
t_x = np.array([[9, 2, 5, 0, 0],
                [7, 5, 0, 0 ,0]])
x_sum = np.sum(np.exp(t_x), axis=1, keepdims= True)
x_sum
```

![[Pasted image 20240427142159.png]]

for more information check ![[np.sum()]]
