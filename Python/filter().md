Takes a function and an iterable as arguments. Just as the name suggests, the goal of the `filter()` function is to "filter" values out of an iterable.
The `filter()` function accomplishes this goal by applying a passed filtering function to each element in the passed iterable. The filtering function should be a function that returns a boolean value: `True` or `False`. Then returned `filter` object will hold only those elements of the passed iterable for which the filtering function returned `True`.

![[Pasted image 20240809202423.png]]

Let's see what this looks like in practice with a function that filters a collection of names and returns only the names that start with the letter  `M` or `m`:
```Python
names = ["margarita", "Linda", "Masako", "Maki", "Angela"]

M_names = filter(lambda name: name[0] == "M" or name[0] == "m", names)

print(list(M_names))
```

Output:
```
['margarita', 'Masako', 'Maki']
```

In this example:
1. `filter()` takes two parameters: the lambda filtering function and the list, `names`.
2. The `filter()` function the iterates through `names` and applies the lambda function to each item in the list.
3. For each item in the list, if the condition in the lambda function evaluates to `True`, the item is added to a `filter` object.
4. 