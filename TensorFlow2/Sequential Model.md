The [[Keras API]] sequential class can use it to built simple models. 
Most of the neural networks can be built using the sequential class.

First wee import the Sequential class and the Dense from the keras layers 
```Python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
```

The way we built a model is very simple. We only need to create an instance of the sequential class. And pass it a list of keras layers. This model is a feedforward network with a single hidden layer. When we call a dense layer we have to pass:
- The number of units we are going to need
- The activation function. By default is the linear activation function.

```Python
model = Sequential([
		Dense(64, activation = 'relu'),
		Dense(10, activation = 'softmax')
])
```
In the model above we are not specifying the number of inputs we are going to feed the network with. We can leave this until the training stage when we feed the data into the model before the weights and bias are created.

Alternatively we can specify the shape of the input data at the built stage.
```Python
model = Sequential([
		Dense(64, activation = 'relu', input_shape=(784,)),
		Dense(10, activation = 'softmax')
])

```

Also we can create the same model above with the following syntax
```Python
model = Sequential()
model.add(Dense(64, activation = 'relu', input_shape = (784,)))
model.add(Dense(10, activation = 'softmax'))
```
Here we are appending aech layer to the model.
