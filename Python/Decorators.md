

```Python
def title_decorator(print_name_function):
	def wrapper():
		print("Professor:")
		print_name_funtion()
	return wrapper


def print_my_name():
	print("Mike")


decorated_function = title_decorator(print_my_name)
decorated_function()
```

with the `@` symbol we can simplify our syntax:
```Python
def title_decorator(print_name_function):
#Here we add arguments to be able to pass different arguments into the function
	def wrapper(*args, **kwargs):
		print("Professor:")
		print_name_funtion(*args, **kwargs)
	return wrapper

@title_decorator 
def print_my_name(name, age):
	print(name + "you are" + str(age))

print_my_name("Shelby", 50)
```

Output:
```
Professor:
Shelby you are 50
```

