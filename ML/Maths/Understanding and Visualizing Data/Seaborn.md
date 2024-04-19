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

## Visualizing the Data - Tables

^fad6d3

One of the most useful ways to begin the analysis is to visualize the data.
```Python
import seaborn as sns #For plotting
import matplotlib.pyplot as plt # For showing plots

#Next we read the data from the filesystem and use it to construct a Pandas dataframe

tips_data = sns.load_dataset("tips")
```

^5cd50b

When you begin working with a new data set, it is often useful to inspect the first few rows of data. This will show you what kind of data is in the dataset, what data types you are working with, and will serve as a reference for the other plots that we produce below.

```Python
tip_data.head()
```
![[Pasted image 20240419174505.png]]

