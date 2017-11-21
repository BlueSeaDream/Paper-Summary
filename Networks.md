### Depthwise Separable Convolution

https://medium.com/towards-data-science/types-of-convolutions-in-deep-learning-717013397f4d

This will perform a spatial convolution while keeping the channels separate and then follow with a depthwise convolution.
In my opinion, it can be best understood with an example. Let’s say we have a 3x3 convolutional layer on 16 input channels
and 32 output channels. What happens in detail is that every of the 16 channels is traversed by 32 3x3 kernels resulting in 
512 (16x32) feature maps. Next, we merge 1 feature map out of every input channel by adding them up. Since we can do that 32 
times, we get the 32 output channels we wanted.


For a depthwise separable convolution on the same example, we traverse the 16 channels with 1 3x3 kernel each, giving us 16 
feature maps. Now, before merging anything, we traverse these 16 feature maps with 32 1x1 convolutions each and only then 
start to them add together. This results in 656 (16x3x3 + 16x32x1x1) parameters opposed to the 4608 (16x32x3x3) parameters
from above.


The example is a specific implementation of a depthwise separable convolution where the so called depth multiplier is 1.  
This is by far the most common setup for such layers. We do this because of the hypothesis that spatial and depthwise 
information can be decoupled. Looking at the performance of the Xception model this theory seems to work. Depthwise separable
convolutions are also used for mobile devices because of their efficient use of parameters. 

### Very Deep Convolutional Networks for Large Scale Image Recognition

https://arxiv.org/pdf/1409.1556.pdf

It is easy to see that a stack of two 3×3 conv. layers (without spatial pooling in between) has an effective receptive field of 5×5; three such layers have a 7 × 7 effective receptive field. So what have we gained by using, for instance, a stack of three 3×3 conv. layers instead of a single 7×7 layer? First, we incorporate three non-linear rectification layers instead of a single one, which makes the decision function more discriminative. Second, we decrease the number of parameters: assuming that both the input and the output of a three-layer 3 × 3 convolution stack has C channels, the stack is parametrised by 3(3^2C^2)= 27C^2 weights; at the same time, a single 7 × 7 conv. layer would require 7^2C^2 = 49C^2 parameters, i.e. 81% more. This can be seen as imposing a regularization on the 7 × 7 conv. filters, forcing them to have a decomposition through the 3 × 3 filters (with non-linearity injected in between). 


The incorporation of 1 × 1 conv. layers (configuration C, Table 1) is a way to increase the nonlinearity of the decision function without affecting the receptive fields of the conv. layers. Eventhough in our case the 1 × 1 convolution is essentially a linear projection onto the space of the same dimensionality (the number of input and output channels is the same), an additional non-linearity is introduced by the rectification function. It should be noted that 1×1 conv. layers have recently been utilised in the “Network in Network” architecture of Lin et al. (2014).

### Darknet19 in YoloV2

https://arxiv.org/pdf/1612.08242.pdf

Darknet-19. We propose a new classification model to be used as the base of YOLOv2. Our model builds off of prior work on network design as well as common knowledge in the field. Similar to the VGG models we use mostly 3x3 filters and double the number of channels after every pooling step. Following the work on Network in Network (NIN) we use global average pooling to make predictions
as well as 1x1 filters to compress the feature representation between 3x3 convolutions. We use batch normalization to stabilize training, speed up convergence, and regularize the model. Our final model, called Darknet-19, has 19 convolutional layers and 5 maxpooling layers. For a full description see Table 6. Darknet-19 only requires 5.58 billion operations to process an image yet achieves 72:9% top-1 accuracy and 91:2% top-5 accuracy on ImageNet.

### DenseNet

https://arxiv.org/pdf/1608.06993.pdf

As CNNs become increasingly deep, a new research problem emerges: as information about the input or gradient
passes through many layers, it can vanish and “wash out” by the time it reaches the end (or beginning) of the
network.

We propose an architecture that distills this insight into a simple connectivity pattern: to ensure maximum
information flow between layers in the network, we connect all layers (with matching feature-map sizes) directly
with each other. To preserve the feed-forward nature, each layer obtains additional inputs from all preceding layers
and passes on its own feature-maps to all subsequent layers.

A possibly counter-intuitive effect of this dense connectivity pattern is that it requires fewer parameters than traditional
convolutional networks, as there is no need to relearn redundant feature-maps. 

Besides better parameter efficiency, one big advantage of DenseNets is their improved flow of information and gradients throughout the network, which makes them easy to train. Each layer has direct access to the gradients from the loss function and the original input signal, leading to an implicit deep supervision.

Further, we also observe that dense connections have a regularizing effect, which reduces overfitting on tasks with smaller training set sizes.
