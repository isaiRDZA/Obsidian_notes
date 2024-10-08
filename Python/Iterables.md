An object that is capable of being looped through one element at a time.
For the following information

| Dog Food Brand     | Quantity |
| ------------------ | -------- |
| Great Dane Foods   | 4 bags   |
| Mini Pip Pup Foods | 10 bags  |
| Pawsome Foods      | 8 bags   |
Using a dictionary, our data would take this form:

```Python
dog_foods = {
	"Great Dane Foods": 4,
	"Min Pin Pup Foods": 10,
	"Paesome Pups Foods": 8
}
```

Now if we wanted to display all the dog brands and their respective quantities, we could use a common loop such as the `for` loop to accomplish this goal. Our program might look something like this:

```Python
for food_brand in dog_foods:
	print(food_brand + " has "
	+ str(dog_foods[food_brand] + " bags"))
```

## Iterator Objects: [[__iter__()]] and [[iter()]]

Under the hood, the first step that the `for` loop has to do is to convert our dictionary (the iterable) of `dog_foods` to an iterator object. An iterator object is a special object that represents a stream of data that we can operate on. To accomplish this, it uses a built-in function called `iter()`:

```Python
dog_food_iterator = iter(dog_foods)
```

We can see the new object by printing it:
```Python
print(dog_food_iterator)
```

This would output our new iterator object:
```
<dict_keyiterator object at 0x>
# Note: The memory address is omitted since it varies on the system you run the script on
```
Here is a visual representation:

![[Pasted image 20240813192902.png]]
To go behind the scenes even further, `iter(dog_foods)` is actually calling a method defined within the iterable called `__iter__()`. All iterables have this `__iter__()`method defined. We can even use the Python built-in function `dir()` to show that our `dog_foods` dictionary (iterable) has a defined method called `__iter__()`

```Python
print(dir(dog_foods))
```

The built-in function `iter()` and the iterable's method `__iter__()` can be used intercahngeably.

The iterator object has a method called `__next__()`, which retrieves the iterator's next value, Let's take a look using our SKU iterable for our shop:

```Python
sku_list = [7046538, 8289407, 9056375, 2308597]
sku_iterator = iter(sku_list)
next_sku = sku_iterator.__next__()
print(next_sku)
```
Output:

```
7046538
```

There is a Python built-in function called `next()` that we can use in place of calling the `__next__()` method. Calling `next()` simply calls the iterator object's `__next__()` method. Here is the same script but using `next()`

```Python
sku_list = [7046538, 8289407, 9056375, 2308597]
sku_iterator = iter(sku_list)
next_sku = next(sku_iterator)
print(next_sku)
```
Output:

```
7046538
```

`__next__()` method will raise an exception called `StopIteration` when all items have been iterated through.

```Python
sku_list = [7046538, 8289407, 9056375, 2308597]
sku_iterator = iter(sku_list)
for i in range(5):  
	next_sku = sku_iterator.__next__()  
	print(next_sku)

```
Output:

```

7046538
8289407
9056375
2308597

Traceback (most recent call last):
  File "main.py", line 24, in <module>
    next_sku = sku_iterator.__next__()
StopIteration

```


