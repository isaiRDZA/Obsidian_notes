A histogram is a way to display the shape of a distribution.

![[Pasted image 20240419115638.png]]

When a histogram is right skewed the mean is normally larger than the median.

## Creating a Histogram

^9fa637

```Python
sns.displot(df.CWDistance)
```
![[Pasted image 20240419170334.png]]

![[Quantitative Data#^98f5fd]]

A histogram captures the shape of the distribution of the data.
```Python
sns.histplot(tips_data["total_bill"], kde = False).set_tittle("Histogram of Total Bill")
```
![[Pasted image 20240419180708.png]]

```Python
sns.histplot(tips_data["tip"], kde = False).set_title("Histogram of Total Tip") 
```
![[Pasted image 20240419180946.png]]

The tips are bivariate -- each customer has both a total bill value and a tip value. This allows us to plot one of these variables abillgainst the other in a scatterplot. I is natural to expect the tip to be larger when the total bill is larger. This relationship is evident in the scatterplot below.

```Python
sns.scatterplot(x='total_', y = 'tip', data=tips_data);
```
![[Pasted image 20240419181239.png]]

We wish to stratify ouur data to some factor, such as the sex of the customer. In this case, we would be able to see if there are systematic differences in tipping behavior or bill size between sexes.
```Python
sns.scatterplot(x = 'total_bill', y = 'tip', hue= 'sex', data= tips_data);
```
![[Pasted image 20240419181449.png]]

