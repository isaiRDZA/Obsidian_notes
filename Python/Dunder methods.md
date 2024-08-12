When working with different object types like, `int`, `str` or `list`, the `+` operator performs different functions. This is known as operator overloading and is another form of polymorphism.
```Python
#For an int and and int, + return an int
2 + 4 == 6

#For a string and a string, + return a string
"Is this " + "addition?" == "Is this addition?"

#For a list and a list, + returns a list
[1, 2] + [3, 4] == [1, 2, 3, 4]
```
To implement this behavior, we must first discuss dunder methods. Every defined class in Python has access to a group of these special methods.
We've explored a few already, the constructor `__init__()` and the string representation method `__repr__()`. The name dunder  method is derived from the **D**ouble **UNDER**scores that surround the name of each  method.
Recall that the `__repr__()` method takes only one parameter, `self`, and must return an string value. The returned value should be a string representation of the class, which can be seen by using `print()` on an instance of the class.
Defining a class's dunder methods is a way to perform operator overloading.
```Python
class Animal:
	def __init__(self, name):
		self.name = name

	def __repr__(self):
		return self.name

	def __add__(self, another_animal):
		return Animal(self.name + another_animal.name)



```
