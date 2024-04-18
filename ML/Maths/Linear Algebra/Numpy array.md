A Python [[list]] is convinient, as you can store different data types.
However, Python lists are limited in functions and take up more space and time to process than NumPy arrays.
NumPy provides an [[array]] object that is much faster and compact than Python lists. Through its extensive [[API]] integration, the library offers many built-in functions that make computing much easier with onlu a few lines of code. This can be huge advantage when performing math operations on large datasets.


The array object in NumPy is called ndarray meaning 'n-dimension array'. A 1-D array represents a standard list of values entirely in one dimension. In Numpy, all of the elements within the array are of the same type.

```Python
one_dimensional_arr = np.array([10, 12])
print(one_dimensional_arr)
```