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
