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

