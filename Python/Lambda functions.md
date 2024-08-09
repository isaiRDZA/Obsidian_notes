In Python, a lambda function (also commonly called an anonymous function) is a one-line shorthand for function.
```Python
def add_two(my_input):
	return my_input + 2
```

The same function could be written as a lambda function:
```Python
add_two = lambda my_input: my_input + 2

print(add_two(3))
print(add(100))
```
Would output:
```
5
102
```

Parts of the lambda function
1. The function is stored in a variable called `add_two`.
2. The lambda keyword declares that this is a lambda function (similar to how we use `def` to declare a normal function).
3. `my_input` is a parameter used to hold the value passed to `add_two`.
4. In the lambda function version, we are returning `my_input + 2` without the use of a `return` keyword (the normal Python function explicitly uses the keyword `return`)

## Conditional if statement in lambda function
We can use a conditional if statement in a lambda function, with syntax:
```Python
check_if_A_grade = lambda grade: 'Got an A!' if grade >= 90 else 'Did not get an A.'
```

Description of code:
1. `Lambda grade:` declares a lambda function with the parameter grade
2. Return `Got an A!` if the statement is true:
```
grade >= 90
```
3. Otherwise, return `Did not get an A.`

## Pros of lambda functions:

1. The reduced syntax assist code readability
2. Functions can be implemented where code reuse is not the primary objective.
