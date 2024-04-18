Slicing gives you a sublist of elements that you specify from the array. The slice notation specifies a start and end value, and copies the list from start up to but not including the end (end-exclusive)

The sintax is:
array'\[start: end: step\]
If no value is passed to sart, it is assumed start = 0, if no value is passed to end. it is assumed that end = lenght of array -1 and if no value is passed to step, it is assumed step = 1.

![[Indexing#^d4b1e8]]

```Python
#Slice the array a to get the array [2, 3, 4]
sliced_arr = a[1:4]
print(sliced_arr)
```
\[2, 3, 4\]

```Python
#Slice the array a to get the array [1, 2, 3]
sliced_arr = a[:3]
print(sliced_arr)
```

```Python
#Slice the array to get the array [3, 4, 5]
sliced_arr = a[2:]
print(sliced_arr)
```

```Python
#Slice the array a to get the array [1, 3, 5]
sliced_arr = a[::2]
print(sliced_arr)
```
## Slicing two dimensional arrays

![[Indexing#^651549]]
```Python
#Slice the two_dim array to get the first two rows
sliced_arr_1 = two_dim[1:3]
sliced_arr_1
```
array\(\[\[1, 2, 3],
       \[4, 5, 6]])

[[Slicing rows]]
```Python
#Slice the two_dim array to get the last two rows
sliced_two_dim_rows = two_dim[1:3]
print(sliced_two_dim_rows)
```
\[\[4 5 6]
 \[7 8 9]]
 
[[Slicing columns]]
```Python 
sliced_two_dim_cols = two_dim[:,1]
print(sliced_two_dim_cols)
```
[2 5 8]