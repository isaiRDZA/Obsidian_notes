```Python
global_variable = 'global'

def add(num_1, num2):
	nested_value = 'Inside Function'
	print(num1 + num2)

add(5, 10)
```
Here, we defined two values: a `global_variable` and a `add()` function. In Python, whenever the interpreter executes a function, it will generate a local namespace for that specific function. This namespace only exist inside of the function and remains in existence until the function terminates.

Python provides a built-in function called `locals()` to see any generated local namespace. 

```Python
global_variable = 'global'

def add(num_1, num2):
	nested_value = 'Inside Function'
	print(num1 + num2)
	print(locals())

add(5, 10)
```

Output:

```
15
{'num1': 5, 'num2': 10, 'nested_value': 'Inside Function'}

```

We can notice the following:
- We called `locals()` inside the `add()` function to get the local namespace generated when the functions is executed. If we called `locals( )` outside of a function in our program, it behaves the same as `globals()`.
- The value printed from calling `locals()` represents the namespace that only exist inside the function. Notice even the function parameters `um1` and `num2` exist along side the variable name `nested_value`. The namespace does not include `global_variable` since it exist outside of the function.