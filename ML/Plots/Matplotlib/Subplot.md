In [[Matplotlib]] we can have many different [[Subplot]] in the same figure, and we can lay them out in many different ways. We can think of out layouts as having rows and columns of subplots.
We can create subplots using .subplot( ) that needs three arguments:
- The number of rows of subplots
- The number of columns of subplots
- The index of the subplot we want to create
```python
#Data sets
x = [1, 2 , 3, 4]
y = [1, 2, 3, 4]

#Fist subplot
plt.subplot(1, 2, 1)
plt.plot(x, y, color = 'green')
plt.title('First Subplot')

#Second Subplot
plt.subplot(1, 2, 2)
plt.plot(x, y, color = 'steelBlue')
plt.title('Second Subplot')

plt.show()
```
![[Pasted image 20231220151856.png]]