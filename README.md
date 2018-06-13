# Mnist-data-numpy-format

This data is originally from [the mnist database](http://yann.lecun.com/exdb/mnist/).
I have formatted it in the following way for ease of use in my tutorial series:

#### mnist.npz contains 6 files:
    'training_images', 'training_labels', 'test_images', 'test_labels', 'validation_images', 'validation_labels'

The image files are each stored as an array of 784x1 arrays.

The label files are each stored as an array of 10x1 arrays (one-hot encoding)

#### The data can be loaded like so (assumes mnist.npz is in same folder as your script):
```python
import numpy as np

with np.load('mnist.npz') as data: 
	training_images = data['training_images']
```

Depending on your setup you may have to use the absolute path to the file, which can be done like so:
```python
import numpy as np
import os

path = os.path.join(os.path.dirname(os.path.realpath(__file__)), 'mnist.npz')
with np.load(path) as data: 
	training_images = data['training_images']
```
