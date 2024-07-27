
[[Variable number of arguments]]
Python doesn't stop at allowing us to accept unlimited positional arguments; it also give us the power to define functions with unlimited keyword arguments. The syntax is very similar but uses two asterisks ** instead of one. We typically call these kwargs as a shorthand of keyword arguments.
```Python
def arbitrary_keyword_args(**kwars):
	print(type(kwargs))
	print(kwargs)
	#See if there is an 'anything_goes' keyword arg and print it
	print(kwargs.get('anything_goes'))
	arbitrary_keyword_args(this_arg = 'wowzers', anything_goes=101)
```
Would output
```
<class 'dict'>
{'this_arg': 'wowzers', 'anything_goes'
: 101}
101
```

We can observe two things:
- `**kwargs` takes the form of a dictionary with all the keyword argument values passed to `arbitrary_keyword_args`. Since `**kwargs` is a dictionary, we can use standard dictionary functions like `.get()` to retrieve values.
- 