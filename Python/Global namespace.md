It includes all non-nested names in the module (file) we are choosing to run the Python interpreter on. The global namespace is created when we run out main program and has a lifetime until the interpreter terminates (usually when our program is finished running). For example, take this program:

```Python
#imaginary file: main.py

firt_name = 'Jaya'
last_name = 'Bodegard'

def print_variable():
	random_number = random.randint(8,9)
	print(first_name)
	print(last_name)
	print(random_number)
```

Our script consist of a few different variables, a function, and an imported module. Right off the bat, it might not be cleat what exist in the global namespace. Thankfully, in order to see what objects exist in the global namespace, Python provides the `globals( )` built-in function.

```Python
print(globals())
```
The output:
```
{'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x7f224a7ae4c0>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': 'main.py', '__cached__': None, 'random': <module 'random' from '/usr/lib/python3.8/random.py'>, 'first_name': 'Jaya', 'last_name': 'Bodegard', 'print_variables': <function print_variables at 0x7f224a76a1f0>}
```
There are only two things we should focus on:

1. The global namespace contains all of the non-nested objects of our program. This includes the variables `first_name` and `last_name` as well as the function `print_variables`. However, the `random_number` variable is not included in the namespace because it is nested inside of our function.

2. Anytime we use the import statement to bring a new module into our program, instead of adding every name from that module (such as all the names in the `random` module) to our current global namespace. Python will create a new namespace for it. This means there might be potentially multiple global namespaces in a single program. This will be masked away from us the format seen with the `random` module (`'random': <module 'random' from '/usr/lib/python3.8/random.py'>`).