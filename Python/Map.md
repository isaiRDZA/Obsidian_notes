The `map()` higher-order function has the following base structure:
```Python
returned_map_object = map(function, iterable)
```
When called `map()` applies the passed function to each and every element in the iterable and returns a `map` object. The returned `map` object holds the results from applying the mapping function to each element in the passed iterable. We will usually convert the `map` into a list to enable viewing and further use.
![[Pasted image 20240809193104.png]]

```Python
def double(x):
	return x*2

int_list = [3, 6, 9]
doubled = map(double, int_list)
print(doubled)
```

Output:
```
<map at 0x7f1ca0f58090>
```

In our example:
1. We defined a function called `double()` that takes in a value and returns the value doubled. This function can be used anywhere in our program-not only with `map()`.
2. We also defined an iterable (`int_list`) that we wanted to apply the function to.
3. We then passed the function reference `double` as the function argument and `int_list` as the iterable to `map()`.
4. The `map()` function proceeded to apply `double()`onto each element in `int_list`.
5. When we printed the result, we could see that the output of the `map()` function was a specific type of object called a `map` object.

If we wan to see the actual results of mapping `double()` to the elements of `int_list`, we need to convert the `map` object to a list using the built-in `list()` function:

```Python
print(list(doubled))
```
This would output:
```
[6, 12, 18]
```

Higher-order functions like `map()` work especially well with lambda functions. Because lambda functions are anonymous, we don't need to define a new named function for `map()` if that function won't be used again elsewhere. In this case, if we don't plan on reusing `double()` somewhere else in our program, we can rewrite the `double()` function from the previous example with a lambda function like so:

```Python
doubled = map(lambda input: input*2, int_list)

print(list(doubled))
```
Output:
```
[6, 12, 18]
```

Using a lambda function with `map()` produced the same output as when the custom `double()` function was passed to `map()`, but it only required one line of code instead of three. 

#### Exercise
Say we stored out course grades in a list, but some of the grades were on a four-point scale (where students score between 0.0 and 4.0) and others were on a 100-point scale (where the students score between 0 and 100).
To get all the grades on the same scale, try using a lambda function inside of the `map()` function. Multiply the grades on the four-point scale by 25 to convert the grades to a 100-point-scale.

```Python
grade_list = [3.5, 3.7, 2.6, 95, 87]

#Your coude below:
grades_100scale = map(lambda grade: grade if grade > 4 else grade*25,grade_list)

#assign the result of your map function to the variable grades_100scale

#Convert grades_100scale to a list and save it as upgraded_grade_list
update_grade_list = (list(grade_correcter))
#print updated_grade_list
print(updated_grade_list)
```
