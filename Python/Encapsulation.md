Encapsulation is the process of making methods and data hidden inside the object they relate to.
Languages accomplish this with what are called access modifiers like:
- Public
- Protected
- Private

In general, public members can be accessed from anywhere, protected members can only be accessed from code within the same module and private members can only be accessed from code within the class that these members are defined.
Python doesn't have any builtin mechanism to prevent access from any member (i.e. all members are public in Python). However, there is a common convention among developers to use a single underscore `self._s` to indicate that the member is protected. Accessing a protected member outside of the module will not cause an error, it is added by developers to inform other developers that they should be careful when accessing this member in such a manner.
Similarly, we can declare a member as private with two leading underscores `self.__x`. This is more than just convention in Python because of a mechanism called name mangling. Members that are preceded with two underscores have their names modified in the background to `obj._Classname__x`. While they can still be publicly accessed, the purpose of this mechanism is to prevent clashing members names of any inheriting classes that might define a member of the same name.
Note that this is different from the [[Dunder methods]].
A dunder method has two leading and two trailing underscores and is treated differently than a private member. One important difference is that dunder method names are not mangled.

 ```Python
calss Employee():
	def __init__(self):
	self._id = "Kevin Kaarl"
	self.__id = "Ed Maverick"


e = Employee()
print(dir(e))
print(e.__Employee__id)
 ```