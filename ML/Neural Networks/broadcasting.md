Imagine we wan to calculate the number of calories for each macro-nutrient of the following foods without using a for loop:
![[Pasted image 20240501152141.png]]

First we would calculate a vector $\vec{c}$ of (1,4) where we are going to sum all the calories for each food:
![[Pasted image 20240501152803.png]]
Then we will divide each row vector by the result of the previous sum for each food, and multiply with 100:
```Python
import numpy as np

A = np.array([[56.0, 0.0, 4.4, 68.0],
             [1.2, 104.0, 52.0, 8.0],
             [1.8, 135.0, 99.0, 0.9]])

cal = A.sum(axis = 0)
print(cal)
print(cal.shape)
```
![[Pasted image 20240501153026.png]]
```Python
percentage = 100*A/cal.reshape(1,4)
print(percentage)
```
![[Pasted image 20240501153101.png]]
