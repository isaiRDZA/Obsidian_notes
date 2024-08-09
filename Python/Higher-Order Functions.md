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
Higher-order functions operate on other functions via arguments or via return values 
