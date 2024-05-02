[[Numpy]] method:
Parameters:
- *a*: Elements to sum
- *axis*: Axis or axes along which a sum is performed. The default, axis=None, will sum all of the elements of the input array. If axis is negative it counts from the last to the first axis. If axis is a tuple of ints, a sum is performed on all of the aces specified in the tuple instead of a single axis or all the axes as before.
- keepdims: bool, optional. If is set to True, the axes which are reduced are left in the result as dimensions with size one. With this option, the result will broadcast correctly against the input array. If the default value is passed, then keepdims will not be passed through to the sum method of sub-classes of ndarray, however any non-default value will be. If the sub-class' method does not implement *keepdims* any exceptions will be araised.
![[Pasted image 20240501221144.png]]

