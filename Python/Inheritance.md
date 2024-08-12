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

## Overriding Mehods

When implementing inheritance, a child class may want to change the behavior of a method from its parent class. In Python, all we have to do is override a method definition. An overriding method in a subclass is one that has the same definition as the parent class but contains different behavior.

