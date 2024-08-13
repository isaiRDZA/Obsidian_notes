

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

Notice that we need to call the methods instead of directly interacting with the weight attribute. What if we could have the best of both worlds? That is, a way to directly interact with the weight attribute but still benefit from the complex behavior of methods such as the weight restriction. This is where the built-in function `property()` comes in.

## The built-in property() function
The Python built-in `property()` function accepts four optional arguments: `fget`, `fset`, `fdel`, and `doc`. The first three represent getter, setter and deleter methods, respectively, and the last one is a docstring for the attribute.
Let's take a look at the advantages by refactoring our `Box` class:
```Python
class Box:
	def __init__(self, weight):
		self.__weight = weight

	def getWeight(self):
		return self.__weight

	def setWeight(self, weight):
		if weight >= 0:
			self.__weight = weight

	def delWeight(self):
		del self.__weight

	weight = property(getWeight, setWeight, delWeight, "Docstring for the 'weight' property")
	
	```

Notice we have added one additional method to out class called `delWeight()`ti serve as a deleter for the property. While it is not strictly required, we will add it to show the full potential of the property() function. We then call the `property()` function and pass the getter, setter and deleter in as arguments. This will imediately allow us to use the following syntax for our class:

```Python
box = Box(10)
print(box.weight) #this calls. getWeight()

box.weight = 5 #this called .setWeight()

del box.weight #this calls .delWeight()

box.weight = -5 #box.__weight is unchanged


```

With this change, our program gains some immediate benefits:
- We can now use the `weight` attribute as if it was public, We no longer have to call the setters, getters and deleter methods directly and this giving our program a simpler syntax.
- Even though we no longer call the methods directly, we still can maintain constraints such as the weight limit in `setWeight()`. It's the best of both worlds!
- If we had a huge codebase that used our methods multiple times in multiple places, a single change to the method name would seriously mess up our program since we would have to change it everywhere! We no longer have this issue using the `property()` method since we never call it directly.

While this is a big advantage for our programs to be more "pythonic", we can go even further by using the decorator patter to replace the need to call the `property()` function altogether.

## @property Decorator
The most pythonic way to define getters, setters, and deleters is by using the `@property` decorator. This decorator is syntactic sugar for using the `property()` function and helps our code look much cleaner. Let's take a look:
```Python
class Box:
	def __init__(self, weight):
		self.__weight = weight

	@property
	def weight(self):
		"""Docstring for the `weight` property"""
		return self.__weight


	@weight.setter
	def weight(self, weight):
		if weight >= 0:
			self.__weight = weight

	@weight.deleter
	def weight(self):
		del self.__weight
		
```

Let's break this down:

- First, we have renamed all of out methods to simply be `weight()`.
- Then we denoted our getter with `@property`. This marks the property to be used as a prefix for decorating the setter and deleter methods.
- Lastly, we use `@weight.setter` and `@weight.deleter` to define our setter and deleter methods, respectively.

This is the equivalent of doing:
```Python
weight = property(getWeight, setWeight, delWeight, "Docstring for the 'weight' property")
```

And this giving us the same syntactical advantage as before:
```Python
box = Box(10)
box.weight = 5
del box.weight
```