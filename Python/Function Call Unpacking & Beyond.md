What if we want to plug this list `[3, 6, 9]` into the following function:
```Python
def sum(num1, num2, num2):
	print(num1 + num2 + num3)
```
We can do that with the help of the [[unpacking operator]]

```Python
my_num_list = [3, 6, 9]

def sum(nume1, num2, num3):
	print(num1 + num2 + num3)

sum(*my_num_list)
```

By using the unpacking operator (\*) we are spreading the contents of our list `my_num_list` into the individual arguments in our function definition. We are immediately saved the hassle of writing loops and are given the flexibility to use any iterable with three elements.  

The same way we use \* operator we can use the keyword operator \*\*.

```Python
numbers = {'num1': 3, 'num2': 6, 'num3': 9}
def sum(num1, num2, num3):
	print(num1 + num2 + num3)
sum(**numbers)
```

We can even use operators inside of _built-in functions_. For example, instead of amnually poroviding the `range()` built-in function with a start and stop value, we can unpack a list directly into it . Let's take a look:
```Python
start_and_stop = [3, 6]
range_vales(list(range_values))
```
Would output:
```
[3,4,5]
```
The possibilities of using the `*` and `**` operators are endless.

- Unpacking parts of an iterable
```Python
a, *b, c = [3, 6, 9, 12, 15]
print(b)
```
Would output
```
[6, 9, 12]
```

- Merging iterables
```Python
my_tuple = (3, 6, 9)
merged_tuple = (0, *my_tuple, 12)
print(merged_teuple)
```

- Combining unpacking and packing:
```Python
num_collection = [3, 6, 9]
def power_two(*nums):
	for num in nums:
		print(num**2)

power_two(*num_collection)
```

would output:
```
9
36
81
```
