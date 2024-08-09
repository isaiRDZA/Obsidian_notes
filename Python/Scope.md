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
Enclosing scope allows any value defined in an enclosing function to be accessed in nested functions below it. We can observe this scope since `nested_function()`