Process of augment the number of elements in a matrix (normally in an image).
![[Padding 2024-06-17 19.42.15.excalidraw]]
In tensorflow there exist 
- padding = 'same': get the correct size for the original image to pass into the [[Convolution]] or [[Pooling]] and preserve the same size after it. 
- padding = 'valid': Does not apply any padding.