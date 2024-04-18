To zoom a [[plot]] in [[Matplotlib]] we can use plt.axis( ) we need to feed this function with a [[list]] that shall contain:
- The minimum x-value displayed.
- The maximum x-value displayed.
- The minimum y-value displayed.
- The maximim y-value displayed.
For example, if we want to display a plot from x = 0 to x = 3 and from y = 2  to y = 5, we would call plt.axis(\[0, 3, 2, 5\]).
```Python
x = [0, 1, 2, 3, 4]
y = [0, 1, 4, 9, 16]
plt.plot(x,y)
plt.axis([0, 3, 2, 5])
plt.show()
```
![[Pasted image 20231220150219.png]]