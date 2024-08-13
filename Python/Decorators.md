

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

## Property Decorator
The @property decorator is a way to use [[Getters, Setters and Deleters]] in our object-oriented programs.
Getters and setters are useful tools for achieving encapsulation (a way to prevent data from direct modification). We can define a private attribute and then use getters and setters to expose a public means of reading and modifying a class attribute value. Further, getters and setters methods allow us to create complex behavior such as limiting access under certain conditions or imposing restriction on allowable ranges of values for an attribute.

```Python
class Box:
	def __int__(self, weight):
		self._weight = weight

	def getWeight(self):
		return self.__weight

	def setWeight(self, weight):
		if weight >= 0:
			self__weight = weight
```

Notice two things:

- We want to follow best practices by denoting weight as a private attribute using __ (dunder) notation. This, however does not make an attribute private, and we can still manipulate it directly.
- We are also posing some restrictions on our setters so that the weight of an instance of the `Box` class can only be set to values grater than zero. We can see this if we try to manipulate an instance:

```Python
box = Box(10)

box.setWeight(-5)
print(box.getWeight())

box.setWeight(5)
print(box.getWeight())
```
That our box weight was unchanged on the first call:
```
10
5
```

Notice that we need to call the methods instead of directly interacting with the weight attribute. What if we could have the best of both worlds? That is, a way to directly interact with the weight attribute but still benefit from the complex behavior of meth