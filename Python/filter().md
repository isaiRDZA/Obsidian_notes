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
4. The `filter` object is returned and when converted to a list and printed, we saw that it contained `['margarita', 'Masako', 'Maki']`-only M-names!
### Example
We were given a list of lists, where each sublist holds the title of a famous book that has a year as its title and the last name of the author that wrote the book.
Unfortunately, when this list was made, each of the books was accidentally entered twice-once with the title as a numeric value and once with the title as a string. Use the filter() function to deduplicate the list and keep only the sublists that have the book title stored as a string:
```Python
books = [["Burgess", 1985],
["Orwell", "Nineteen Eighty-four"],
["Murakami", "1Q85"],
["Orwell", 1984],
["Burgess", "Nineteen Eighty-five"],
["Murakami", 1985]]


# Your code below:

string_titles = filter(lambda l: type(l[1]) == str, books)

# convert your filter object to a list stored in the variable string_titles_list

string_titles_list = list(string_titles)
  
# print the list string_titles_list
print(string_titles_list)
```
