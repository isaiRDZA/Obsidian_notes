Python knows `print()`, `str()` in all of the programs because they exist in the highest level of namespaces and thus can be called in any program we write.
Whenever we run a Python application, we are provided a built-in namespace that is created when the interpreter is started and has a lifetime until the intepreter terminates (usually when our program finished running)

We can see what is in the built-in namespace by running the following code

```Python
print(dir(__builtins__))
```