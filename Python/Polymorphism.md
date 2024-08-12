The ability to apply an identical operation onto different types of objects.
```Python
class Employee():
	new_id = 1
	
	def __init__(self):
		self.id = Employee.new_id
		Employee.new_id += 1


	def say_id(self):
		print("My id is {}.".format(self.id))
	

class Admin(Employee):
	
	
	def say_id(self):
		super().say_id()
		print("I am an admin.")


class Manager(Admin):
	def say_id(self):
		super().say_id()
		print("I am in charge!")

e1 = Employee()
e2 = Admin()
e3 = Manager()
meeting = [e1, e2, e3]

for e in meeting:
	e.say_id()

```

Output:
```
My id is 1.
My id is 2.
I am an admin.
My id is 3.
I am an admin.
I am in charge!
```

The example above shows how each class has a method `say_id()` with different outputs. The identical method name with different behaviors is a form of polymorphism.
Another type of polymorphism can be seen with the help of [[Dunder methods]]