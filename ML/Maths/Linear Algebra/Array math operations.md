[[Numpy]] allows you to quickly perform elementwise adition,, substraction, multiplication and division for both 1-D and multidimensional arrays. The operations are performed using the math symbol for each '+', '-' and '\*'. Recall that adition of Python lists works completely different as it would append the lists, thus making a longer list, in addition, substraction and multiplication of Python lists do not work.
```Python
import numpy as np

arr_1 = np.array([2, 4, 6])
arr_2 = np.array([1, 3, 5])

# Adding two 1.D arrays
addition = arr_1 + arr_2
print(addition)

#Subtracting two 1-D array
subtraction = arr_1 - arr_2
print(subtraction)

#Multipying wo 1-D arrays elementwise
multiplication = arr_1 * arr_2
print(multiplication)
```
\[ 3  7 11\]
\[1 1 1\]
\[ 2 12 30\]
