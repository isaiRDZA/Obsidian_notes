Enclosing namespaces are created specifically when we work with [[nested functions]] and just like with the local namespace, will only exit until the function is done executing.
```Python
global_variabel = 'global'

def outer_function():
	outer_value = 'outer'
	def inner_function():
		inner_value = 'inner'

inner_function()

outer_function()
```

In this program, the following occurs:

- We define a function called `outer_function()` and nest another function inside it called `inner_function()`. To generate a namespace, functions must be executed, so we are calling both of them.
- Here, The `outer_function()` serves the role of an enclosing function while `inner_function` is an enclosed function. By creating this structure, we generate an enclosing namespace - a namespace created by an enclosing function and any number of enclosed functions inside it.

While Python doesn't give us any particular function like `enclosing()` to visualize the namespace, we can use `locals()` to see when enclosed namespace are generated. Let's take a look by modifying our script:

```Python
global_variable = 'global'

def outer_function():
	outer value = 'outer'
	def inner_function():
		inner_value = 'inner'
	inner_function()
	#Added locals output
	print(locals())
outer_function()
```

would output:
```
{'outer_value': 'outer', 'inner_function': <function outer_function.<locals>.inner_function at 0x7f46b56bc820>}
```

## Practice example
```Python
global_variable = 'global'

def outer_function():
	outer_value = "outer"

	def inner_function():
		inner_value = "inner"

		def inner_nested_function():
			nested_value = 'nested'
			print(locals())

		inner_nested_function()

		# Add locals() below
		print(locals())

	inner_function()

outer_function()
```

Output:
```
{'nested_value': 'nested'}
{'inner_nested_function': <function outer_function.<locals>.inner_function.<locals>.inner_nested_function at 0x7f435189be18>, 'inner_value': 'inner'}
```