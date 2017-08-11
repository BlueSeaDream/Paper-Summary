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


| Network | Model Size | Average Percision | Time (ms) | Comments |
| --------|------------|-------------------|------|--|
| YoloV2 | | 21.6 | 25 | |
| SSD (321x321) | | 28.0 | 61 | |
| DSSD (321x321) | | 28.0 | 85 | |
| R-FCN | | 29.9 | 85 | |
| SSD (513x513) | | 31.2 | 125 | |
| DSSD (513x513) | |33.2 | 156 | |
| FPN FRCN | |36.2 | 172 | |
|RetinaNet-50-500 | | 32.5 | 73 | |
|RetinNet-101-500 | | 34.4 | 90 | |
|RetinaNet-101-800 | | 37.8 | 198 | |
