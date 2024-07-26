In [[Matplotlib]] we can label the x- and y-axes by using polt.xlabel() and plt.ylabel(). The plot title can be set by using plt.title().
All of these commands require a [[string]].
Example of track of [[happinesss]].
```python
hours = [9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
happiness = [9.8, 9.9, 9.2, 8.6, 8.3, 9.0, 8.7, 9.1, 7.0, 6.4, 6.9, 7.5]
plt.plot(hours, hapiness)
plt.xlabel('Time of day')
plt.ylabel('Hapiness Rating (out of 10)')
plt.titlte('My Self-Reported Hapineess While Awake')
plt.show()
```
![[Pasted image 20231220150917.png]]

