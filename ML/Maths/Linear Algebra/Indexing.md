Indexing is very useful as it allows you to select specific elements from an array. It also lets you select entire rows/columns or planes.

Let us select specific elements from the arrays as given
```Python
#Select the third element of the array. Remember the counting starts from 0.
a = ([1, 2, 3, 4, 5])
print(a[2])

#Select the first element of the array
print(a[0])
```

^d4b1e8

3
1

For multidimensional arrays of shape n, to index a specific element, you must input n indices one for each dimension.

```Python
#Indexing on a 2-D array
two_dim = np.array(([1, 2, 3],
				  [4, 5, 6],
				  [7, 8, 9]))
#Select element number 8 from the 2-D array using indices i,j
print(two_dim[2][1])
```

^651549

8


