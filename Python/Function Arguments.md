In Python, there are three common types of function arguments:
- Positional arguments: arguments that are called by their position in the function definition.
- Keyword arguments: arguments that are called by their name.
- Default arguments: arguments that are given default values.

## Positional arguments
```Python
def print_name(first_name, last_name):
	print(first_name, last_name)
print_name('Jiho', 'Baggins')
```
Here, `first_name` will be mapped to `'Jiho'` while `last_name` will be mapped to `'Baggins'` due to the position of the arguments when calling the function.

## Keyword Arguments

```Python
def print_name(first_name, last_name):
	print(first_name, last_name)


print_name(last_name = 'Baggins', first_name = 'Jiho')
```

## Default arguments
```Python
def print_name(first_name = 'Jiho', last_name = 'Baggins')
	print(first_name, last_name)

print_name()
```