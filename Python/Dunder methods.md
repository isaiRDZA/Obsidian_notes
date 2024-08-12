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


a1 = Animal("Horse")
a2 = Animal("Penguin")
a3 = a1 + a2

print(a1)
print(a2)
print(a3)
```
The above code has the class `Animal` with a dunder method, `.__add__()`. This defines the `+` operator behavior when used on objects of this class type. The method returns a new `Animal` object with the name of the operands objects concatenated. in this example, we have created a `"HorsePenguin"`!

The line of code `a3 = a1 + a2` invokes the `.__add__()` method of the left operand, `a1`, with the right operand `a2` passed as an argument. The `name` attributes of `a1` and `a2` are concatenated using the `.__add_()`parameters, `self`and `another_animal`. The resulting string is used as the name of a new `Animal` object which is returned to become the value of `a3`
```Python
class Employee:
	new_id = 1
	def __init__(self):
		self.id = Employee.new_id
		Employee.new_id += 1

class Meeting:
	def __init__(self):
		self.attendees = []
	def __len__(self):
		return len(self.attendees)
	def __add__(self, employee):
		print("ID {} added".format(employee.id))
		self.attendees.append(employee)


e1 = Employee()
e2 = Employee()
e3 = Employee()
m1 = Meeting()
m1+e1
m1+e2
```