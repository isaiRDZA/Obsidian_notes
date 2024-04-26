Two common numpy function used in deep learning are np.shape and np.reshape().
- X.shape  is used to get the shape (dimension) of matrix/vector X.
- X.reshape(...) is used to reshape X into some other dimension.

For example in computer science, an image is represented by a 3D array of shape (*lenght, height, deoth = 3*). However, when you read an image as the input of an algorithm you convert it to a vector of shape (*lenght x height x 3, 1*). In other words, you "unroll", or reshape, the 3D array into a 1D vector.

![[Pasted image 20240426134611.png]]

**numpy.reshape(a, newshape, order = 'c')**

**newshape** : int or tuple of ints
The new shape should be compatible with the original shape. If an integer, then the result will be a 1-D array of that length. One shape dimension can be -1. In this case, the value is inferred from the length of the array and remaining dimensions.

```Python
import numpy as np
t_image = np.array([[[ 0.67826139,  0.29380381],
                     [ 0.90714982,  0.52835647],
                     [ 0.4215251 ,  0.45017551]],

                   [[ 0.92814219,  0.96677647],
                    [ 0.85304703,  0.52351845],
                    [ 0.19981397,  0.27417313]],

                   [[ 0.60659855,  0.00533165],
                    [ 0.10820313,  0.49978937],
                    [ 0.34144279,  0.94630077]]])

t_image = t_image.reshape((t_image.shape[0]*t_image.shape[1]*t_image.shape[2]))
print(t_image)
t_image.shape
```
![[Pasted image 20240426142458.png]]


Example
Implementing image2vector() a function that takes an input of shape (lenght, height, 3) and returns a vector of shape (lenght \* height \* , 3) and returns a vector of shape (lenght \* height \* 3, 1). 


![[Multidimensional Array#^574301]]
![[Multidimensional Array#^f7a42f]]