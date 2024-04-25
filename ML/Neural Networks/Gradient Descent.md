This algorithm looks for the values of $\omega$ and $b$ that minimize the [[Cost function]] 

![[Pasted image 20240424224212.png]]

## Algorithm
1. Initialize random or to zero the $\omega$ and $b$ values
2. Takes a step into the steepest downhill direction, and update $\omega$
3. Iterate the step two until reach close to the global optimal

Repeat{
	$\omega = \omega - \alpha \frac{\partial J(\omega)}{\partial w}$
}

for updating b:
Repeat{
	$b = b - \alpha \frac{\partial J(w,b)}{\partial b}$
}
Where:
$\alpha$ : is the learning rate, control how big is the next step.