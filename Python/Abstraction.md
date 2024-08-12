Abstraction helps with the design of code by defining necessary behaviors to be implemented within a class structure. By doing so, abstraction also helps avoid leaving out or overlapping class functionality as class hierarchies get larger.

```Python
from abc import ABC, abstractmethod

class Animal(ABC):
	def __init__(selfm, name):
	self.name = name


	@abstractmethod
	def make_noise(self):
		pass

class Cat(Animal):
	def make_noise(self):
		print("{} says, Meow!".format(self.name))

class Dog(Animal):
	def make_noise(self):
		print("{}")
```