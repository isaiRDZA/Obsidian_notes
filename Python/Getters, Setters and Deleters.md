Using getter, setter, and deleter functions are one way to implement encapsulation within Python where the states of class attributes can be handled within the class. These functions are useful in making sure that the data being handled is appropriate for the defined class functionality.
```Python
class Animal:
	def __init__(self, name):
		self._name = name
		self.age = None

	def get_age(self):
		return self._age

	def set_age(self, new_age):
		if isinstance(new_age, int):
			self._age = new_age
		else:
		raise TypeError


	def delete_age(self):
		print("_age Deleted")
		del self._age

```
Looking at the `Animal` class above there is an `_age` attribute with a single underscore. This notates it is intended to be used only within the module. There are then 3 methods related to `age` each with a different purpose. These define the getter, setter, and deleter of the specific property.
The first method related to `age` is a getter and returns `self._age`. The setter is implemented below that. It includes logic that ensures that the value passed to `new_age` is and integer. If so, `self._age = new_age`. If not, raise an error. This is useful and shows the power of using these functions for encapsulation.
The deleter is implemented below the setter. It outputs a confirmation message and uses the `del` keyword to delete the `self._age` attribute.
```Python
a = Animal("Rufus") #None

a.set_age(10)
print(a.get_age()) # 10

a.set_age("Ten") # Raises a TypeError

a.delete_age() # "_age Deleted"
print(a.get_age()) # Raises a AttributeError
```

Above we see `a.get_age()` gets the `_age` value, `a.set_age(10)` sets the value and `a.delete_age()`