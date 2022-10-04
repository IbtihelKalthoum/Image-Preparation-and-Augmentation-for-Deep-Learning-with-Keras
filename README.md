# Image-Preparation-and-Augmentation-for-Deep-Learning-with-Keras
Keras is an open-source high-level Neural Network library, written in Python and running on 
top of the machine learning platform.
## 1 Installation and Setup
Being the fact that Keras runs on the top of Tensorflow, we need to install TensorFlow first.
## 2 Keras Image Augmentation API
Keras provides the ImageDataGenerator class that defines the configuration for image data preparation and augmentation.

- Horizontal and Vertical Shift Augmentation
Perform vertical shifts of the image via the height_shift_range=0.5 argument. It specifys
the percentage of the image to shift as 0.5 the height of the image.
We can notice that in some cases the replicated pixels at the edge of the image may not make 
sense to a model.

- Horizontal and Vertical Flip Augmentation
Image flipping reverses the rows or columns of pixels in the case of a vertical or horizontal 
flip respectively. The flip augmentation is specified by the argument
horizontal_flip=True or vertical_flip=True to 
the ImageDataGenerator() constructor.

- Random Rotation Augmentation
A rotation augmentation rotates the image clockwise randomly by a given number of degrees 
from 0 to 360.
Perform random rotations to the image between 0 and 90 degrees via 
the rotation_range=90 argument to the ImageDataGenerator() constructor.

- Random Brightness Augmentation
The brightness of the image can be augmented by either randomly darkening images, 
brightening images, or both. This can be achieved by specifying 
the brightness_range argument to the ImageDataGenerator() constructor. Values less 
than 1.0 darken the image, whereas values larger than 1.0 brighten the image. 
Perform a brightness image augmentation, allowing the generator to randomly darken the image 
between 1.0 (no change) and 0.3.

- Random Zoom Augmentation
Perform a zooming image augmentation be configuring the
argument zoom_range=[0.5,1.5] to the ImageDataGenerator() constructor.

## 3 Application to MNIST Handwritten Digit Dataset
- Feature Standardization
It is possible to standardize pixel values across the entire dataset. (Note: Standardization is often 
performed for each column in a tabular dataset).
We can perform feature standardization by setting the
arguments featurewise_center=True and featurewise_std_normalization=True to 
the ImageDataGenerator() constructor.

- Image Whitening
An image whitening is a linear operation that reduces the redundancy in images. Less 
redundancy is intended to better highlight the structures and features in the image to the learning 
algorithm.

-Random Rotations, Shifts and Flips
Add these image augmentations to the ImageDataGenerator() constructor (see above 
subsection)

-Saving Augmented Images to File
