## Characteristics
- Boxplots provide us a very nice graphical picture of our five-number summary.
- Boxplots show us the center through the median.
- The inter-quartile range is the lenght of the box.
- Boxplots have an algorithm to help identify [[outliers]].
## Descriptions

| Min | Q1  | Median | Q3  | Max |
| --- | --- | ------ | --- | --- |
|     |     | Center |     |     |
         <--------IQR-------->
<----------------Range---------------->

## Examples

![[Pasted image 20240419091701.png]]

![[Pasted image 20240419092049.png]]

To make a boxplot in python we need the seaborn library:

```Python
sns.boxplot(data=df.loc[:, ["Age","Height", "Wingspan", "CWDistance", "Score"]])
```

![[Pasted image 20240419165022.png]]

```Python
#A box only of females
sns.boxplot(data=df.loc[df['Gender'] == 'F', ['Age', 'Height', 'Wingspan', 'CWDistance', "Score"]])
```

![[Pasted image 20240419165821.png]]

```Python
#A boxplot only of males
sns.boxplot(data=df.loc[df['Gender'] == 'M', ['Age', 'Height', 'Wingspan', 'CWDistance', "Score"]])
```
![[Pasted image 20240419170032.png]]


## Visualizing data
Histograms require a lot of data to produce accurate estimates of the population density (which is what the histogram is estimating). Boxplots show a minimal amount of information about the shape of a distribution and can be more informative with smaller datasets.

Below we create a boxplot of the bill amount. The median bill is around 18 dollars, and half of the bills fall between 12 and 24 dollars (approximately). Extreme bills may be as large as 40 dollars, with a small number of bills being even larger than 40 dollars.
![[Histograms#^9fa637]]

```Python
sns.boxplot(x=tips_data["total_bill"]).set_title("Box plot of the Total Bill")
```
![[Pasted image 20240419182241.png]]

Next we create a boxplot of t tip amounts
```Python
sns.boxplot(x = tips_data['tips']).set_title("Box plot of the Tips")
```
![[Pasted image 20240419182451.png]]

## Creating histograms and box plots stratified by groups
While looking at a single variable is interesting, it is often useful to see how a variable changes in coordination with another. Using graphs, we can see if there is a difference between the tipping amounts of smokers vs non-smokers, or if tipping varies according to the time of the day
```Python
#Create a boxplot and histogram of the tips grounded by smoking status
sns.boxplot(x = tips_data["tip"], y = tips_data["smoker"])
plt.show()
```
![[Pasted image 20240419184109.png]]

```Python
#Create a boxplot and histogram of the tips grouped by time of day
sns.boxplot(x = tips_data['tip'], y = tips_data['time'])
```
![[Pasted image 20240420004253.png]]

We can also compare the tip distributions based on wether the tip was paid for lunch or dinner.
```Python
g = sns.FacetGrid(tep_data, row = 'time')
g = g.map(plt.hist, "tip")
plt.show()
```
![[Pasted image 20240420004506.png]]

Next we look at the distribution of tips by day of week, using boxplots to show the main features of the distributions.

```Python
sns.boxplot(x = tips_data['tip'], y = tips_data['day'])
```

![[Pasted image 20240420004716.png]]

Histograms can capture more features of a distribution, but if the sample is small a histogram may be quite imprecise.

```Python
g = sns.FacetGrid(tips_data, row = 'day')
g = g.map(plt.hist, "tip")
plt.show()
```
![[Pasted image 20240420005050.png]]
