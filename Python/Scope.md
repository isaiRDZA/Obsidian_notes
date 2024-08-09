![[Pasted image 20240808190356.png]]

## Local Scope
Since the local scope is the deepest level of the four scopes, names in a local scope cannot be accessed or modified by any code called in outer spaces.
```Python
def favoutirte_color():
	color = 'Red'

print color
```
In this case the name of `color` is scoped locally to the function `favourite_color()`. Since the statement `print(color)` is called outside of the function, it has no access to the local scope (and this the local namespace) inside of `favourite_color()` and returns an error.
We shall refactor our function:

```Python
def favourite_color():
	color = 'Red'
	print(color)

favourite_color()
```

# Enclosing/Nonlocal scope
Enclosing scope allows any value defined in an enclosing function to be accessed in nested functions below it. We can observe this scope since `nested_function()` can access a variable defined one level above in the enclosing function (`outer_function()`).
```Python
def outer_function():
	enclosing_value = 'Enclosing Value'
	def nested_function():
		nested_value = 'Nested Value'
		print(enclosing_value)
	nested_function()

outer_function()
```

The output
`Enclosing value`

We can also observe this scoping rule further if we nested a function one level deeper:
```Python
def outer_function():
	enclosing_value = 'Enclosing Value'
	
	def nested_function():
		nested_value = 'Nested Value'
		
		def second_nested():
			print(enclosing_value)
			print(nested_value)
		
		second_nested()
	
	nested_function()

outer_function()

outer_function()
```

The output:
```
Enclosing Value
Nested Value
```

# There are two caveats to be aware of with enclosing scope:

- The flow of scope access only flows upwards. This means that the deepest level has access to every enclosing namespaces above it, but not the other way around. For example, if we tried to access `nested value` from one leve above where it was defined
```Python
def outer_function():
	enclosing_value = 'Enclosing Value'
	print(nested_value)

	def nested_function():
		nested_value = 'Nested Value'

	nested_function()

outer_function()
```

The program would produce an error:
```Python
NameError: name 'nested_value' is not defined
```

- **Immutable objects, such as [[strings]] or numbers, can be accessed in nested functions, but cannot be modified.**
```Python
def outer_function():
	enclosing_value = 'Enclosing Value'

	def nested_function():
		enclosing_value += 'changed'

	nested_fucntion()
	print(enclosing_value)


outer_fucntion()
```

Would output:
```
UnboundLocalError: local variable 'enclosing_value' referenced vefore assignment
```
