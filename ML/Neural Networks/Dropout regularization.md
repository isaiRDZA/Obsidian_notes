Dropout is another method to apply [[Regularization]] to reduce [[high variance]] or [[overfitting]]
![[Excalidraw/Dropout regularization|Dropout regularization]]
## Implementing dropout ("Inverted dropout")
We are going to apply a drop out to the layer 3 with a probability of dropout  = 0.2. However, we have to set the probability of keeping a node.
`keep_prob = 0.8`
`d3 = np.random.rand(a3.shape[0],a.shape[1] < keep_prob`
d3 is going to be a boolean matrix, then when multiply with a3, the results of the layer 3 will be set to 0 for the nodes that we calculate to disconect.
`a3 = np.multiply(a3, d3)`
Then to keep the value of a3, we are going to divide its value by keep_prob.
`a3 /= keep_prob`


##
dimensions of $w^{[1]}$ should be 7x3 
dimensions of $w^{[3]}$ should be 3x7