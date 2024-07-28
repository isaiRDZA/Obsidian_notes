```Python
color = "cyan"
```
Here we assign `color` as the **name** of the string `"cyan"`.
Python uses the system of names so that it can differentiate between each distinct object (such as a string or a function) that we define.
In most programs, Python has to keep track of the hundreds and sometimes even thousands of names. 

For this propose, Python creates what is call **namespace**.
A namespace is a collection of names and the objects that they reference. Python will host a dictionary where the keys are the names that have been defined and the mapped values are the objects that they reference.

In the example above, the namespace Python creates would look something like this:
```
{'color':'cyan'}
```

There exist four distinct types of namespaces that Python generates:
1. [[Built-in namespace]] 
2. [[Global namespace]]
3. [[Local namespace]]
4. [[Enclosing namespace]]
![[Pasted image 20240727204029.png]]
