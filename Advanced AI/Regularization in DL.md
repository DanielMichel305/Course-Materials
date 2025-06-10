# Regularization in Deep Learning

#### Why do We do Regularization in the Context of DL?
DL models require large amounts of data to regularize and actually learn and not just overfit.

##### Methods of Regularization may include (not limited to) :
- Image Augmentation 
- Neuron Dropout


### Image Augmentation

Image Augmentation involves modifying existing images in the dataset to create "New" Images that can be useful when Training set isn't large enough.

###### Examples of Image Augmentation:
- Image flipping
- Rotaion
- Image Crop/cutout
- Lighting Transformations (Hue, Brightness, Contrast, etc...)
- Many more

### Neuron Dropout

###### Problem that Dropout solves:
**Co-adaptation** which is when multiple Neurons in the same layer extract the same or closely similar Features which poses the following main problems

- If multiple Neuron Extract the same feature then this tricks the model to think that they have high significance, which leads to Overfitting in some cases
- Wasted Compute resources 

Dropout uses a probability P that is the probability that a specific neuron will be turned off during  each iteration.

author: [@DanielMichel305](https://github.com/DanielMichel305)
11/6/2025