### The PASCAL Visual Object Classes
http://host.robots.ox.ac.uk/pascal/VOC/


2012 20 classes. The train/val data has 11,530 images containing 27,450 ROI annotated objects and 6,929 segmentations.

### COCO Common Objects in Context

COCO 2017 Detection Challenge

http://cocodataset.org/#detections-challenge2017

The COCO train, validation, and test sets, containing more than 200,000 images and 80 object categories, are available on the download page. All object instances are annotated with a detailed segmentation mask. Annotations on the training and validation sets (with over 500,000 object instances segmented) are publicly available.

###  Large Scale Visual Recognition Challenge 2017 (ILSVRC2017)
http://image-net.org/challenges/LSVRC/2017/#det

I: Object localization

The data for the classification and localization tasks will remain unchanged from ILSVRC 2012 . The validation and test data will consist of 150,000 photographs, collected from flickr and other search engines, hand labeled with the presence or absence of 1000 object categories. The 1000 object categories contain both internal nodes and leaf nodes of ImageNet, but do not overlap with each other. A random subset of 5


II: Object detection

The training and validation data for the object detection task will remain unchanged from ILSVRC 2014. The test data will be partially refreshed with new images based upon last year's competition(ILSVRC 2016). There are 200 basic-level categories for this task which are fully annotated on the test data, i.e. bounding boxes for all categories in the image have been labeled. The categories were carefully chosen considering different factors such as object scale, level of image clutterness, average number of object instance, and several others. Some of the test images will contain none of the 200 categories. Browse all annotated detection images here.0,000 of the images with labels will be released as validation data included in the development kit along with a list of the 1000 categories. The remaining images will be used for evaluation and will be released without labels at test time. The training data, the subset of ImageNet containing the 1000 categories and 1.2 million images, will be packaged for easy downloading. The validation and test data for this competition are not contained in the ImageNet training data.

###MINIST

深度学习和机器学习领域的“Hello World!”！MNIST是一个入门级的计算机视觉数据集，它包含各种尺寸是28*28的手写数字图片，它有60000个训练样本集和10000个测试样本集。此数据集是以二进制存储的，不能直接以图像格式查看，不过很容易找到将其转换成图像格式的工具。

最早的深度卷积网络LeNet便是针对此数据集的，当前主流深度学习框架几乎无一例外将MNIST数据集的处理作为介绍及入门第一教程。

训练数据集的图片是 mnist.train.images。mnist.train.images 是一个形状为 [60000, 784] 的张量，第一个维度数字用来索引图片，第二个维度数字用来索引每张图片中的像素点。在此张量里的每一个元素，都表示某张图片里的某个像素的强度值，值介于0和1之间。
训练数据集的标签是 mnist.train.labels。MNIST数据集的标签是介于0到9的数字，用来描述给定图片里表示的数字。
数据集大小：~12MB

下载地址：http://yann.lecun.com/exdb/mnist/index.html

###Imagenet

MNIST将初学者领进了深度学习领域，而Imagenet数据集对深度学习的浪潮起了巨大的推动作用。深度学习领域大牛Hinton在2012年发表的论文《ImageNet Classification with Deep Convolutional Neural Networks》在计算机视觉领域带来了一场“革命”，此论文的工作正是基于Imagenet数据集。

Imagenet数据集有1400多万幅图片，涵盖2万多个类别；其中有超过百万的图片有明确的类别标注和图像中物体位置的标注。

Imagenet数据集是目前深度学习图像领域应用得非常多的一个领域，关于图像分类、定位、检测等研究工作大多基于此数据集展开。Imagenet数据集文档详细，有专门的团队维护，使用非常方便，在计算机视觉领域研究论文中应用非常广，几乎成为了目前深度学习图像领域算法性能检验的“标准”数据集。

与Imagenet数据集对应的有一个享誉全球的“ImageNet国际计算机视觉挑战赛(ILSVRC)”，以往一般是google、MSRA等大公司夺得冠军，（2016）ILSVRC2016中国团队包揽全部项目的冠军。

Imagenet数据集是一个非常优秀的数据集，但是标注难免会有错误，几乎每年都会对错误的数据进行修正或是删除，建议下载最新数据集并关注数据集更新。

###COCO

COCO(Common Objects in Context)，是一个新的图像识别、分割和图像语义数据集，它有如下特点：

1. Object segmentation
2. Recognition in Context
3. Multiple objects per image
4. More than 300,000 images
5. More than 2 Million instances
6. 80 object categories
7. 5 captions per image
8. Keypoints on 100,000 people

COCO数据集由微软赞助，其对于图像的标注信息不仅有类别、位置信息，还有对图像的语义文本描述，COCO数据集的开源使得近两三年来图像分割语义理解取得了巨大的进展，也几乎成为了图像语义理解算法性能评价的“标准”数据集。

Google开源的图说生成模型show and tell就是在此数据集上测试的，想玩的可以下下来试试。

数据集大小：~40GB
下载地址：http://mscoco.org/

###PASCAL VOC

PASCAL VOC为图像识别和分类提供了一整套标准化的优秀的数据集，是视觉对象的分类识别和检测的一个基准测试，提供了检测算法和学习性能的标准图像注释数据集和标准的评估系统。PASCAL VOC图片集包括20个目录：人类；动物（鸟、猫、牛、狗、马、羊）；交通工具（飞机、自行车、船、公共汽车、小轿车、摩托车、火车）；室内（瓶子、椅子、餐桌、盆栽植物、沙发、电视）。PASCAL VOC挑战赛在2012年后便不再举办，但其数据集图像质量好，标注完备，非常适合用来测试算法性能。

数据集大小：~2GB
下载地址：
http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html

###CIFAR

CIFAR-10是由 Hinton 的两个大弟子 Alex Krizhevsky、Ilya Sutskever 收集的一个用于普适物体识别的数据集，包含10个类别，60,000张32x32 RGB彩色图像，其中50,000张用于训练，10,000张用于测试。这个数据集最大的特点在于将识别迁移到了普适物体，而且应用于多分类。
CIFAR-100与CIFAR-10类似，包含100个类，每类有600张图片，其中500张用于训练，100张用于测试；这100个类分组成20个超类。图像类别均有明确标注。CIFAR对于图像分类算法测试来说是一个非常不错的中小规模数据集。

数据集大小：~170MB
下载地址：
http://www.cs.toronto.edu/~kriz/cifar.html

###Open Image

过去几年机器学习的发展使得计算机视觉有了快速的进步，系统能够自动描述图片，对共享的图片创造自然语言回应。其中大部分的进展都可归因于 ImageNet 、COCO这样的数据集的公开使用。谷歌作为一家伟大的公司，自然也要做出些表示，于是乎就有了Open Image。

Open Image是一个包含900万张图像URL的数据集，里面的图片通过标签注释被分为6000多类。该数据集中的标签数量远远大于ImageNet（1000类），因此它足够让我们训练出一个强大的深度神经网络。该唯一不足的可能就是它只是提供图片URL，使用起来可能不如直接提供图片方便。

数据集大小：~1.5GB（只是链接，不包括图片）
下载地址：https://github.com/openimages/dataset
