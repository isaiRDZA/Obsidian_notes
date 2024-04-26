Two common numpy function used in deep learning are np.shape and np.reshape().
- X.shape  is used to get the shape (dimension) of matrix/vector X.
- X.reshape(...) is used to reshape X into some other dimension.

For example in computer science, an image is represented by a 3D array of shape (*lenght, height, deoth = 3*). However, when you read an image as the input of an algorithm you convert it to a vector of shape (*lenght x height x 3, 1*). In other words, you "unroll", or reshape, the 3D array into a 1D vector.

![[Pasted image 20240426134611.png]]

Implementing image2vector() a function that takes an input of shape (lenght, height, 3) and returns a vector of shape (lenght \* height \* , 3) and returns a vector of shape (lenght \* height \* 3, 1).


![[Multidimensional Array#^574301]]
![[Multidimensional Array#^f7a42f]]