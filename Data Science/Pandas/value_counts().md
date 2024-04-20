The value_counts method can be used to determine the number of times that each distinct value of a variable occurs in a data set.
This method produces a table with two columns. The first column contains all distinct observed values for the variable. The second column contains the number of times that each of these values occurs.

```Python
da  = pd.read_csv("nhanes_2015_2016.csv")
da.DMDEDUC2.value_counts()
```
![[Pasted image 20240420011905.png]]
