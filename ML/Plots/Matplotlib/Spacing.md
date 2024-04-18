In [[Matplotlib]] we can customize the spacing between our [[subplot]]s to make sure that the fugure we create is visible and easy to underdstand. To do this, we use the plt.subplots_adjust( ) command, the keyword arguments that can move our plots within the figure:
- **left** - left-side margin, with a default of 0.125. You can increase this nuymber to make room for a y-axis label.
- **right** - the right-side margin, with a default of 0.9 You can increase this to make more room for the figure, decrease it to make room for a legend.
- **bottom** - the bottom margin, with a default of 0.1. You can increase this to make room for tick mark labels or an x-axis label.
- **top** - the top margin, with a default of 0.9
- **wspace** - the horizontal space between adjacent subplots, with a default of 0.2
- **hspace** - the vertical space betweem adjacent subplots, with a default of 0.2

![[Pasted image 20231220154544.png]]

For example:
![[Pasted image 20231220154747.png]]

Ler's use wspace to fit the figure above:
```python
#Left Plot
plt.subplot(1, 2, 1)
plt.plot([-2, -1, 0, 1, 2], [4, 1, 0, 1, 4])

#Right Plot
plt.subplot(1, 2, 2)
plt.plot([-2, -1, 0, 1, 2], [4, 1, 0, 1, 4])

#Subplot Adjust
plt.subplots_adjust(wspace =  0.35)
plt.show()
```
![[Pasted image 20231220155124.png]]
