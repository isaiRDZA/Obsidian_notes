## First-class functions or first-class citizens
1. Can be stored as variables
2. Can be passed as arguments to a function
3. Can be returned by function
4. Can be stored in data structures (list, dictionaries, etc.)
```Python
#Here, we assign a function to a variable
uppercase = str.upper

#And then call it
big_pie = uppercase("pumpkinpie")

#Here we store two functions in a list
string_manipulation_functions = [str.upper, str.lower]
```

The fact that functions are first-class objects in Python, and therefore have all the flexibility of objects, enable us to write even more powerful types of functions called **Higher-order functions**.
Higher-order functions operate on other functions via arguments or via return values. This means higher-order functions do one ore both of the following:
- Accept a function as an argument
- Have a return value that is a function

# Function as arguments - Iteration

We have a list of bills instead of just one. We want to add tax or tip to each bill, depending on the type of sale it is.
One way to accomplish this could be to write out separate loops: one for sales that need to have tax added and one for sales that should have a tip added. To get a sense of what this would look like, let's write out the loop for adding tax first:
```Python
bills = [115, 120, 42]
new_bills = []

for i in range(len(bills)):
	total = add_tax(bills[i])
	new_bills.append("Total amount owed is $:" + "{:.2f}".format(total)+ ". Thank you! :)")

print(new_bills)
```
Would output:
```Python
['Total amount owed is $121.90. Thank you! :)',
'Total amount owed is $127.20. Thank you! :)',
'Total amount owed is $44.52. Thank you! :)']
```
Now, we could write out another loop for when we need to add a tip instead of tax, but we can probably guess how many repetitions would be involved. 
**A much more powerful solution** would be to use a high-order function to apply `add_tax()` or `add_tip()` to each balance in our list. Lets first define a higher-order function, `total_bills()`, that takes a function and a list as arguments, applies the function to each element in the list, standardizes the format of the result and adds a friendly message, appends the output to a new list, and finally returns the updated new list

```Python
def total_bills(func, list):
	#This list will store all the new bill values
	new_bills = []

	for i in range(len(list)):

		#Here we apply the function to each element of the list
		total = func(list[i])
		new_bills.append("Total amount owed is $" + "{:.2f}".format(total) + ". Thank you! :)")
		return new_bills
```

Next, let's use the `add_tax()` function that we wrote before with our new `toral_bills()` higher-order function:
```Python

bills = [115, 120, 42]

bills_w_tax = total_bills(add_tax, bills)

print(bills_w_tax)
```

would output:
```Python
['Total amount owed is $121.90. Thank you! :)', 'Total amount owed is $127.20. Thank you! :)', 'Total amount owed is $44.52. Thank you! :)']

```

And if we need to add a tip instead of tax, we could simply swap out the function argument:

```Python
bills_w_tip = total_bills(add_tip, bills)

print(bills_w_tip)
```

Would output:
```Python

['Total amount owed is $138.00. Thank you! :)', 'Total amount owed is $144.00. Thank you! :)', 'Total amount owed is $50.40. Thank you! :)']

```

As these examples show, being able to pass functions in as arguments can be pretty handy, especially when we want to apply a function multipple times. In fact, it's so handy that there's a built-in higher-order function in Python that does just that-the `map()` function. 

# Functions as Return Values
So far, we have focused on higher-order functions that take another function as an argument. Remember, thought, that a function that returns another function is also higher-order function.
```Python
def make_box_volume_function(height):
	#defines and returns a function that takes two numeric arguments,
	#lengh & width, and returns the volume given the input height
	def volume(lenght, width):
		return lenght*width*height
	
	return volume

box_volume_height15 = make_box_volume_function(15)
print(box_volume_height15(3,2))
```

Output:
```
90
```

And if we had slightly shorter boxes:
```Python
box_volume_height10 = make_box_volume_function(10)

print(box_volume_height10(3,2))
```
Would output:
```
60
```
In the example we:
- Wrote a high-order function `make_box_volume_function()`: It takes a height as an argument and returns a new function that calculates the volume of any box with that height when it is passed the length and width of the box.
- High-order functions with functions as return values are just as re-usables as higher-order functions with functions as arguments, and therefore, also reduce repetition and the chances for mistakes to creep into code,

There are built-in higher-order functions:
1. [[map()]]
2. [[filter()]]
3. [[reduce()]]
