Sometimes, we want to modify a global name from within a local scope.
 ```Python
global_var = 10
def some_function():
	global_var = 20

some_function()

print(global_var)
```

The output would be:
```
10
```
In the above example, the value of `global_val` remains `10` because `global_var = 20` is in a local scope.
similar to the [[nonlocal]] statement, Python provides the global statement to allow the modification of global names from a local scope.

```
global_var = 10

def some_function():
	global global_var
	global_var = 20

some_function()

print(global_var)
```

The output would be:
```
10
```

In addition, the `global` statement can be used even if the name has not been defined in the global namespce. Using the global statement would create the new variable in the global namespace.
```Python
def some_function():
	global x
	x = 30

some_function()
print(x)
```

The output would be:
```
30
```
