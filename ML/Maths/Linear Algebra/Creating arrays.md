	Using the function array( ) which takes in a list of values as an argument and returns a 1-D array.

```Python
#Creaate and print a NumPy array 'a' containing the elements 1, 2, 3
a = np.array([1, 2, 3])
print(a)
```

Another way to implement is using np.arange( ). This function will return an array of evenly spaced values within a given interval.

```Python
#create an array with 3 integers, starting from the default integer 0
b = np.arange(3)
pirnt b
```
\[0 1 2\]

```Python
#Create an array that starts from the integer 1, ends at 20, increment by 3
c = np.arange(1, 20, 3)
print(c)
```
\[ 1  4  7 10 13 16 19\]

If you want to create an [[array]] with five evenly spaced values in the interval from 0 to 100. You have 3 parametes that a function must take.
- The starting number, in this case 0
- The final number, in this case 100
- The number of elements in the array, in this case 5
NumPy has a function that allows you to do specifically this by using np.linespace( )

```Python
lin_spaced_arr = np.linespace(0, 100, 5)
print(lin_spaced_arr)
```
\[  0.  25.  50.  75. 100.\]

The default type for values in the NumPy function np.linespace is a floating point ([[np.float64]]). You can easily specify your data type using dtype. 

```Python
lin_spaced_arr_int = np.linespace(0, 100, 5, dtype = int)
print(lin_spaced_arr_int)
```
\[  0  25  50  75 100\]

```Python
c_int = np_arange(1, 20, 3, dtype = int)
print(c_int)
```
\[ 1  4  7 10 13 16 19\]

```Python
b_float = np.arange(3, dtype = float)
print(b_float)
```
\[0. 1. 2.\]

```Python
char_arr = np.array(['Welcome to Math for ML!'])
print(char_arr)
print(char_arr.dtype)

```
\['Welcome to Math for ML!'\]
\<U23

This mean hat the string 'Welcome to Math for ML!' is a 23.character (23) unicode string (U). More about [data types]([Data types — NumPy v1.26 Manual](https://numpy.org/doc/stable/user/basics.types.html))

One of the advantages of using NumPy is that you can easily create arreys with built in functions.
Such as:
- np.ones( ) Returns a new array setting values to one.
```Python
#Return a new array of shape 3, filled with ones.
ones_arr = np.ones(3)
print(ones_arr)
```
\[1. 1. 1.\]

- np.zeros( ) Returns a new array setting values to zero.
```Python
#Return a new array of shape 3, filled with zeros
zeros_arr = np.zeros(3)
print(zeros_arr)
```
\[0. 0. 0.\]

- np.empty( ) Returns a new unitilized array.
```Python
#Return a new array of shape 3, without initializing entries
empt_arr = np.zeros(3)
pirnt(empr_arr)
```
\[0. 0. 0.\]

- np.random.rand( ) Returns a new array with values chosen at random.
```Python
rand_arr = np.random.rand(3)
print(rand_arr)
```
\[0.02424706 0.5460603  0.40185951\]