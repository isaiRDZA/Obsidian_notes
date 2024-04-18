We can specify a different color for a [[line]] by using the keyword color with either and HTML color name or a HEX code in [[Matplotlib]]:

```python
plt.plot(days, money_spent, color = 'green')
plot.plot(days, money_spent_2, color = '#AAAAAAA')
```
![[Pasted image 20231220121034.png]]
We can also make a line dotted or dashed using keyword linestyle.
 ```python
 #Dashed
 plt.plot(x_values, y_values, linestyle = '--')
 #Dotted:
 plt.plot(x_values, y_values, linestyle = ':')
 #No line:
 plt.plot(x_values, y_values, linestyle = '')
```
We can also add a marker using the keyword  marker: 
```python
#A circle:
plt.plot(x_values, y_values, marker = 'o')
#A square:
plt.plot(x_values, y_values, marker = 's')
#A star:
plt.plot(x_values, y_values, marker = '*')
```
[Matplotlib documentation]([matplotlib.pyplot.plot — Matplotlib 3.8.2 documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot))

Example:
```Python
plt.plot(days, money_spent, color = 'green', linestyle = '--')
plt.plot(days, money_spent_2, color = '#AAAAAA', marker = 'o')
```

![[Pasted image 20231220122156.png]]
#Matplotlib #Graphs #Charts #DataScience