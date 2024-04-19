Seaborn is essentially a high-level interface to Matplotlib that is intended to make statistical data visualization easier. Any plot can be made in Seaborn ca also be made in Matplotlib, but certain types of graphs are easier to make in Seaborn (and some other may be easier to make in Matplotlib).

## Scatterplots
The following plot is a basic scatterplot
```Python
#Store the url string that host our .csv file
url = "Cartwheeldata.csv"

#Read the .csv file and store ir as a pandas Fram
df = pd.read_csv(url)

#Create Scatterpot
sns.scatterplot(x = 'Wingspan', y = 'CWDistance', data = df);

```
![[Pasted image 20240419164122.png]]

Now we add more information to the scatterplot, by plotting females and males in different colors.

```Python 
sns.scatterpot(x = 'Wingspan', y = 'CWDistance', hue = 'Gender', data = df);
```
![[Pasted image 20240419164258.png]]

A "swarmplot" is a type of scatterplot for situations where one variable is categorical. Note that the categorical varibale is "jittered" to reduce overplotting.

```Python
sns.swarmplot(x = 'Gender', y = 'CWDistance', data = df);
```
![[Pasted image 20240419164721.png]]
