```Python
print('This', 'is', 'the', 'print', 'function')
```
Notice how the `print()` function does not care how many arguments we pass to it.

There is an additional operator called the [[unpacking operator (*)]]. The unpacking operator allows us to give our functions a variable number of arguments by performing what's known as [[positional argument packing]].
```Python
def my_fucntion(*args):
prit(args)
```

If we called this function with random arguments, our output would show us what is inside \*args 

The unpacking operator is not limited to being used alone, but rather it can be combined with other positional arguments.