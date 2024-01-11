# VGG16

16 layer neural net

#### Data preprocess

VGG takes in a 224x224 pixel RGB image as input.&#x20;

For the ImageNet competition, the authors cropped out the center 224x224 patch in each image to keep the input image size consistent.

#### Convolution layers

The convolutional layers in VGG use a very small receptive field (3x3, the smallest possible size that still captures left/right and up/down). There are also 1x1 convolution filters which act as a linear transformation of the input, which is followed by a ReLU unit. The padding is 1 and the convolution stride is fixed to 1 pixel so that the spatial resolution is preserved after convolution.

The number of filters increase as we go deeper into the network. The spatial size of the feature maps decrease since we do pooling, but the depth of the volumes increase as we use more filters.

All of VGG’s hidden layers use ReLU (a huge innovation from AlexNet that cut training time). VGG does not generally use Local Response Normalisation (LRN), as LRN increases memory consumption and training time with no particular increase in accuracy.

**Stacking two convolution layers:**

It only uses 3x3 convolutions (no padding) throughout the network. Note that two back to back 3x3 convolutions have the effective receptive field of a single 5x5 convolution. And three stacked 3x3 convolutions have the receptive field of a single 7x7 one.

Another advantage of stacking two convolutions instead of one is that we use two relu operations, and more non-linearity gives more power to the model.

#### Pooling layers

After a convolution operation we usually perform pooling to reduce the dimensionality. This enables us to reduce the number of parameters, which both shortens the training time and combats overfitting. Pooling layers down-sample each feature map independently, reducing the height and width, keeping the depth intact.

#### Fully-connected layers

VGG has three fully-connected layers: the first two have 4096 channels each and the third has 1000 channels, 1 for each class.

## References

1. [VGG Neural Networks: The Next Step After AlexNet](https://towardsdatascience.com/vgg-neural-networks-the-next-step-after-alexnet-3f91fa9ffe2c)
2. [Reading the VGG Network Paper and Implementing It From Scratch with Keras](https://hackernoon.com/learning-keras-by-implementing-vgg16-from-scratch-d036733f2d5)
