In Python, a lambda function (also commonly called an anonymous function) is a one-line shorthand for function.
```Python
def add_two(my_input):
	return my_input + 2
```

The same function could be written as a lambda function:
```Python
add_two = lambda my_input: my_input + 2

print(add_two(3))
print(add(100))
```
Would output:
```
5
102
```
