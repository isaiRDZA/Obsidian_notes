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

