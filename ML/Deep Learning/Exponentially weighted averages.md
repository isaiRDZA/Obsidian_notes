When we have this kind of information we can plot a line with the average of all these data points.
$\theta_{1} = 40°F$
$\theta_{2} = 49°F$
$\theta_{3}=45°F$
$\vdots$
$\theta_{180} = 60° F$
$\theta_{181} = 56°F$
$\vdots$
![[Pasted image 20240516105832.png]]

Applying the following equation:
$$\begin{align}V_{0} = 0
\\V_{1} = 0.9V_{0} + 0.1 \theta_{1}
\\V_{2} = 0.9V_{1}+0.1\theta_{2}
\\V_{3} = 0.9V_{2} + 0.1\theta_{3}
\\ \vdots
\\V_{L} = 0.9V_{t-1} + 0.1\theta_{t}
\\\end{align}$$
And we end up with a plot like the following:
![[Pasted image 20240516110811.png]]
The generalization of this equation is:
$$V_{t} = \beta V_{t-1}+(1-\beta)\theta_{t}$$
the graphic above is generated when $\beta = 0.9$ and this value is approximately to compute the average of 10 days.
To calculate the days in this example we an use the following equation
$$\frac{1}{1-\beta}\ days\ of\ temperature$$
For example with a $\beta = 0.98$ we would be averaging 50 days.
This formula came from the fact that when we start calculating the values of $V_{t}$ , we are multiplying the $\beta$, over and over.
$$\begin{align} 
\\V_{100} = 0.9V_{99}+(0.1)\theta_{100}
\\V_{99} = 0.9V_{98}+(0.1)\theta_{99}
\\V_{98} = 0.9V_{97}+(0.1)\theta_{98}
\\V_{97} = 0.9V_{96}+(0.1)\theta_{97}
\\ \vdots
\\V_{100} = 0.1\theta_{100}+ 0.9(0.1\theta_{99})+ 0.9^{2}(0.1)\theta_{98}+0.9^{3}(0.1)\theta_{97}+\dots
\end{align}$$
So the above formula calculates when the equation term $(1-\beta)$ is equal to a third of its value or equals to $\frac{1}{e} \approx 0.35$.
And we use the equation
$$(1-\epsilon)^{\frac{1}{\epsilon}} = \frac{1}{e}$$
Where for this example:
$\epsilon = 0.1$
$1-\epsilon = 0.9$

