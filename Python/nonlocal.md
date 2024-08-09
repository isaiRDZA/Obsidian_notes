Given the following enclosing and nested function, there is a variable defined in the enclosing scope, which is not modifiable from within the nested function.
```Python
def enclosing_fucntion():
	var = "value"
	def nested_function():
		var = "new_value"

	nested_function()

	print(var)

enclosing_fucntion()
```

Output:
```
value
```

as the value of `var` was not modified by the nested function. After using the `nonlocal` statement, the variable is now modifiable from the local scope.

```Python
def enclosing_function():
	var = 'value'

	def nested_function():
		nonlocal var
		var = 'new_value'

	nested_function()
	print(var)

enclosing_function()
```

Output:
```
new_value
```