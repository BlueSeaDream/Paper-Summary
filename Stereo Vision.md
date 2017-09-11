## Evaluation of Kitti Stereo Dataset
- **D1-bg:** Percentage of stereo disparity outliers averaged over background regions.
- **D1-fg:** Percentage of stereo disparity outliers averaged over foreground regions.
- **D1-all:** Percentage of stereo disparity outliers averaged over all ground truth pixels.
## Evaluation of Middlebury Stereo Dataset
- **R**: RMS (root-mean-squared error) measured in disparity units between the computed disparity map and the ground truth map.
- **D**: Percentage of bad matching pixels with a disparity error tolerance (1 pixel by default).
  In addition to computing R and D over the whole image, three different kinds of regions, i.e. textureless region (T), occluded regions (O), and depth discontinuity regions (D) are used for the evaluation.
