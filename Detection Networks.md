## RetinaNet

**Title:** Focal Loss for Dense Object Detection

**Authors:** Tsung-Yi Lin, Priya Goyal, Ross Girshick, Kaiming He, and Piotr Dollar

**Address:** Facebook AI Research

**Publication:** https://arxiv.org/pdf/1708.02002.pdf

**Excerption**

- Current state-of-the-art object detectors are based on a two-stage, proposal-driven mechanism. As popularized
in the R-CNN framework, the first stage generates a sparse set of candidate object locations and the second stage
classifies each candidate location as one of the foreground classes or as background using a convolutional neural network.
Through a sequence of advances, this two-stage framework consistently achieves top accuracy on the challenging COCO benchmark.

- Class imbalance is addressed in R-CNN-like detectors by a two-stage cascade and sampling heuristics. The proposal stage (e.g., Selective Search, EdgeBoxes, DeepMask, RPN) rapidly narrows down the number of candidate object locations to a small number
(e.g., 1-2k), filtering out most background samples. In the second classification stage, sampling heuristics, such as a
fixed foreground-to-background ratio (1:3), or online hard example mining (OHEM) [30], are performed to maintain a manageable balance between foreground and background.

- In contrast, a one-stage detector must process a much larger set of candidate object locations regularly sampled
across an image. In practice this often amounts to enumerating ~100k locations that densely cover spatial positions,
scales, and aspect ratios. While similar sampling heuristics may also be applied, they are inefficient as the training
procedure is still dominated by easily classified background examples. This inefficiency is a classic problem in object
detection that is typically addressed via techniques such as bootstrapping or hard example mining.


| Network | Model Size (MB) | Average Percision | Top1 | Top5 | Time (ms) | Comments |
| --------|------------|-------------------|------|------|-----------|----------|
| YoloV2 | | 21.6 | | | 25 | | | |
| SSD (321x321) | | 28.0 | | | 61 | | | |  |
| DSSD (321x321) | | 28.0 | | | 85 | | | |
| R-FCN | | 29.9 | | | 85 | | | |
| SSD (513x513) | | 31.2 | | | 125 | | | |
| DSSD (513x513) | |33.2 | | | 156 | | | |
| FPN FRCN | |36.2 | | | 172 | | | |
| RetinaNet-50-500 | | 32.5 | | | 73 | | | |
| RetinaNet-101-500 | | 34.4 | | | 90 | | | |
| RetinaNet-101-800 | | 37.8 | | | 198 | | |

| Network | Model Size (MB) | Top1 | Top5 | Time (ms) | Comments |
| --------|------------|-------------------|------|------|-----------|----------|
| DenseNet 121 | 30.8 | 74.21 | 92.19 | | |
| MobileNet | 16.2 | 70.81 | 89.85 | | |
| ShuffleNet | 7.0 | 62.8 | 84.7 | | |
| ResNet | 102.5   |77 | 90.1 | | |


## Resnet  

**Title:** Deep Residual Learning for Image Recognition

**Authors:** Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun

**Address:** Microsoft Research

**Publication:** https://arxiv.org/abs/1512.03385

**Excerption**

In the paper, He et al. use bottleneck architecture for each the residual block. It means that the residual block consists of 3 layers in this order: 1x1 convolution - 3x3 convolution - 1x1 convolution. The first and the last convolution is the bottleneck. It mostly just for practical consideration, as the first 1x1 convolution is being used to reduce the dimensionality, and the last 1x1 convolution is to restore it. So, the same network is now become 50 layers.

## YOLOV2:
**Titel:** YOLO9000 Better, Faster, Stronger

**Authors:** Joseph Redmon and Ali Farhadi

**Address:** University of Washington, Allen Institute for AI

**Publication:** http://pjreddie.com/yolo9000

**Excerption**

- **Batch Normalization** Batch normalization leads to significant improvements in convergence while eliminating the
need for other forms of regularization [7]. By adding batch normalization on all of the convolutional layers in YOLO
we get more than 2% improvement in mAP. Batch normalization  also  helps  regularize  the  model. With  batch  nor-
malization we can remove dropout from the model without overfitting.

- **High Resolution Classifier** 
For YOLOv2 we first fine tune the classification network at the full 448×448 resolution for 10 epochs on ImageNet. This gives the network time to adjust its filters to work better on higher resolution input. We then fine tune the resulting network on detection. This high resolution classification network gives us an increase of almost 4% mAP.


- **Route Layer**
bring finer grained features in from earlier in the network

- **Reorg Layer**
make finer grained features match the feature map size at the later layer. The end feature map is 13x13, the feature map from earlier is 26x26x512. The reorg layer maps the 26x26x512 feature map onto a 13x13x2048 feature map so that it can be concatenated with the feature maps at 13x13 resolution.

https://medium.com/towards-data-science/yolo-you-only-look-once-real-time-object-detection-explained-492dc9230006

http://blog.csdn.net/hrsstudy/article/details/65447947

-**Region Layer**
YOLO_V2的region_layer LOSS损失计算源码解读

http://blog.csdn.net/dongapple/article/details/76230455


## Mask R-CNN
- **RoIAlign** RoIPool [12] is a standard operation for extracting a small feature map (e.g., 7×7) from each RoI. RoIPool
first quantizes a floating-number RoI to the discrete granularity of the feature map, this quantized RoI is then subdivided
into spatial bins which are themselves quantized, and finally feature values covered by each bin are aggregated
(usually by max pooling). Quantization is performed, e.g., on a continuous coordinate x by computing [x/16], where
16 is a feature map stride and [·] is rounding; likewise, quantization is performed when dividing into bins (e.g., 7×7).
These quantizations introduce misalignments between the RoI and the extracted features. While this may not impact
classification, which is robust to small translations, it has a large negative effect on predicting pixel-accurate masks.
To address this, we propose an RoIAlign layer that removes the harsh quantization of RoIPool, properly aligning
the extracted features with the input. Our proposed change is simple: we avoid any quantization of the RoI boundaries
or bins (i.e., we use x/16 instead of [x/16]). We use bilinear interpolation [22] to compute the exact values of the input
features at four regularly sampled locations in each RoI bin, and aggregate the result (using max or average).

An evaluation of our proposed RoIAlign layer is shown in Table 2c. For this experiment we use the ResNet-50-C4 backbone, which has stride 16. RoIAlign improves AP by about 3 points over RoIPool, with much of the gain coming at high IoU (AP75). RoIAlign is insensitive to max/average pool; we use average in the rest of the paper.   



