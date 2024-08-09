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
**A much more powerful solution** would be to use a high-order function to apply `add_tax()` or `add_tip()` to each balance in our list. Lets first define a higher-order function, `total_bills()`, that takes a function and a list as arguments, applies the function to each element in the list, standadizes 