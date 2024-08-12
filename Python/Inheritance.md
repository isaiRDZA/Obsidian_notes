How can we get a child class inherit methods and attributes from a parent class.
```Python
class ParentClass:
	#something
class ChildClass(ParentClass):
	#class mehtods/properties
```
Example:

```Python

class Employee():
	new_id = 1
	
	def __init__(self):
		self.id = Employee.new_id
		Employee.new_id += 1


	def say_id(self):
		print("My id is []".format(self.id))


clas Admin(Employee):
	pass

e1 = Employee()
e2 = Employee()
e3 = Admin()
e3.say_id()
```

## Overriding Methods

When implementing inheritance, a child class may want to change the behavior of a method from its parent class. In Python, all we have to do is override a method definition. An overriding method in a subclass is one that has the same definition as the parent class but contains different behavior.
 
```Python
clas Employee():
	new_id = 1

	def __init__(self):
		self.id = Employee.new_id
		Employee.new_id += 1


	def say_id(self):
		print("My id is {}".format(self.id))


class Admin(Employee):
	def say_id(self):
		print("I am an Admin")

e1 = Employee()
e2 = Empĺoyee()
e3 = Admin()
e3.say_id()
```

Output:
```
I am an Admin
```

## super()
When overriding methods we sometimes want to still access the behavior of the parent method. In order to do that we need a way to call the method of the parenthesis class. Python gives us a way to do that using `super()`
`super()` gives us a *proxy object*. With this proxy object, we can invoke the method of an object's parent class (also called its superclass). We call the required function as a method on `super()`:

```Python
clas Employee():
	new_id = 1

	def __init__(self):
		self.id = Employee.new_id
		Employee.new_id += 1


	def say_id(self):
		print("My id is {}".format(self.id))


class Admin(Employee):
	def say_id(self):
	super().say_id()
	print("I am an admin")


e1 = Employee()
e2 = Employee()
e3 = Admin()
e3.say_id()
```

Output:
```
My id is 3.
I am an admin.
```

Another example:

```Python
class Animal:
	def __init__(self, name, sound = "Grrr"):
		self.name = name
		self.sound = sound

	def make_noise(self):
		print("{}says, {}".format(self.name, self.sound))


class Cat(Animal):
	def__init__(self, name):
		super().__init__(name, "Meow!")

pet_cat = Cat("Rachel")
pet_cat.make_noise()#Rachel says, Meow!
```

In the above example:
- The `Cat` subclass has an `.__init__()` method which means the `.__init__()` method of its superclass `Animal` will not be called when creating an instance of `Cat`. The `.__init__()` method from the subclass is overriding the one form the superclass.

- The `.__init__()` method of  `Animal` is still invoked when in `super().__init__(name, "Meow!")` is called inside the subclass `.__init__()` method. This additional logic allows us to add the `"Meow"` sound from within the `Cat`classs, but still use the `