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