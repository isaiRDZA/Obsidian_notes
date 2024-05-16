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
