Think if a multidimensional array as an excel sheet where each row/column represents a dimension.
![[Pasted image 20231221105202.png]]

```Python 
#Create a 2 dimensional array(2 - D)
two_dim_arr = np.array([[1,2,3], [4,5,6]])
print(two_dim_arr)
```
![[Pasted image 20231221105614.png]]

An alternative way to create a multidimensional array is by [[Reshaping]] the initial 1-D array. Using np.reshape( ) you can rearrange elements of the previous array into a new shape. ^574301
```Python
#1-D array
one_dim_arr = np.array([1, 2, 3, 4, 5, 6])

#Multidimensional array using reshape( )
multi_dim_arr = np.reshape(
						   one_dim_arr, #the array to be rehaped
						   (2, 3) # dimensions of the new array
						)
print(multi_dim_arr)
```

^f7a42f

^4a8fe3
![[Pasted image 20231221110433.png]]


