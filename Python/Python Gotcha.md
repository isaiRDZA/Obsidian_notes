Gotcha is a counter intuitive feature of a programming language that often leads to mistakes in programs
```Python
def createStudent(name, age, grades = [])
	return{
		'name': name,
		'age' : age,
		'grades' : grades
	}

def addGrade(student, grade):
	student['grades'].append(grade)
	print(student['grades'])


chrisley = createStdent('Chrisley', 15)
dallas = createStudent('Dallas', 16)

addGrade(chrisley, 90)
addGrade(dallas, 100)
```
The actual output is:
```
[90]
[90,. 100]
```


## Mutables and Functions
A mutable object refers to various containers in Python that are intended to be changed.
The mutable objects in python contain methods that allow us to change them, the mutable objects are:
- List
- Dictionary
- Set
When using a mutable is important to remember that this objects are evaluated once they are defined, and that same pre computed value is used for each call.
This means that in the code above, the list grades = [] is created only once, and we can check the memory id and it is going to be the same.

The non mutables are:
- int
- float
- tuples
- strings: When updating a string, the update will return a completely new string

## The None Workaround

```Python
def createStudent(name, age, grades = None):
	if grades is None:
		grades = []
	return{
	'name': name,
	'age': age,
	'grades': grades
	}
def addGrade(student, grade):
	student['grades'].append(grade)
	print(student['grades'])
	
```
Now if we create out students again and add grades to them, each student will have a completely independent list.
