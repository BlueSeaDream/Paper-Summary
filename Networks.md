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