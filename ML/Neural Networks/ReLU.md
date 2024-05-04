The function to calculate ReLU (Rectified Linear Unit ) is

$$ a = max(0, z)$$
![[Pasted image 20240504143748.png]]

This is increasingly the default to choose when you don't know what to chose for your hidden layers.
The disadvantage of ReLU is that the derivarive is negative when $z$ is negative. To solve this the [[Leaky ReLU]] was introdiced

## Derivative
![[Pasted image 20240504163836.png]]