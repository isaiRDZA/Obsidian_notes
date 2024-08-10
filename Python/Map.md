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
4. The `map()`
