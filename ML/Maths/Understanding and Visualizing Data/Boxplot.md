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

