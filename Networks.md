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

It is easy to see that a stack of two
3×3 conv. layers (without spatial pooling in between) has an effective receptive field of 5×5; three such layers have a 7 × 7 effective receptive field. So what have we gained by using, for instance, a stack of three 3×3 conv. layers instead of a single 7×7 layer? First, we incorporate three non-linear rectification layers instead of a single one, which makes the decision function more discriminative. Second, we decrease the number of parameters: assuming that both the input and the output of a three-layer 3 × 3 convolution stack has C channels, the stack is parametrised by 3(3^2C^2)= 27C^2 weights; at the same time, a single 7 × 7 conv. layer would require 7^2C^2 = 49C^2 parameters, i.e. 81% more. This can be seen as imposing a regularization on the 7 × 7 conv. filters, forcing them to have a decomposition through the 3 × 3 filters (with non-linearity injected in between). 


The incorporation of 1 × 1 conv. layers (configuration C, Table 1) is a way to increase the nonlinearity of the decision function without affecting the receptive fields of the conv. layers. Eventhough in our case the 1 × 1 convolution is essentially a linear projection onto the space of the same dimensionality (the number of input and output channels is the same), an additional non-linearity is introduced by the rectification function. It should be noted that 1×1 conv. layers have recently been utilised in the “Network in Network” architecture of Lin et al. (2014).
