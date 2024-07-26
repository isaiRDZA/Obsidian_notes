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


## Muta