[[Numpy]] allow you to join two or more arrays, either horizontally or vertically, meaning that it is done along new axis.
- np.vstack( ) - stacks vertically
- np.hstack( ) - stacks horizontally
- np.hsplit( ) - splits an array into several smaller arrays

```Python
a1 = np.array([[1,1],
			  [2,2]])
a2 = np.array([[3,3],
			  [4,4]])
print(f'a1:\n{a1}')
print(f'a1:\n{a2}')

```
a1:
\[\[1 1]
 \[2 2]]
a2:
\[\[3 3]
 \[4 4]]

```Python
#Stack tha arrays vertically
vert_stack = np.vstack((a1, a2))
print(vert_stack)
```
\[\[1 1]
 \[2 2]
 \[3 3]
 \[4 4]]

```Python
#Stack the arrays horizontally
horz_stack = np.hstack((a1, a2))
print(horz_stack)
```
\[\[1 1 3 3]
 \[2 2 4 4]]