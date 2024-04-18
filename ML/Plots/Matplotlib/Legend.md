In [[Matplotlib]] when we have multiple lines we can laberl then by using the comand plt.legend( )
The [[legend]] method takes a list with the labels to display.
```Python
plt.plot([0, 1, 2, 3, 4], [0, 1, 4, 9, 16])
plt.plot([0, 1, 2, 3, 4], [0, 1, 8, 27, 64])
plt.legend(['parabola', 'cubic'])
plr.show()
```

![[Pasted image 20231220160210.png]]

plt.legend( ) can also take an keyword argument loc, which will position the legend on the figure.
These are the position values loc accepts:

|Number Code|String|
|---|---|
|0|best|
|1|upper right|
|2|upper left|
|3|lower left|
|4|lower right|
|5|right|
|6|center left|
|7|center right|
|8|lower center|
|9|upper center|
|10|center|

For example, we call plt.legend( ) and set loc to 6:
```python
plt.legend(['parabola', 'cubic'], loc = 6)
plt.show()
```
![[Pasted image 20231220160839.png]]

To label each line as we create it:

```Python
plt.plot([0, 1, 2, 3, 4], [0, 1, 4, 9, 16], label = 'parabola')
plt.plot([0, 1, 2, 3, 4], [0, 1, 8, 27, 64], label = 'cubic')
plt.legend() #Still need this comand!
plt.show()
```
![[Pasted image 20231220161108.png]]