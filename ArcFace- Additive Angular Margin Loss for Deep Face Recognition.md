# ArcFace: Additive Angular Margin Loss for Deep Face Recognition

*Deng, Jiankang, et al. "Arcface: Additive angular margin loss for deep face recognition." CVPR 2019.*

## Contribution

1. Propose ArcFace, which has a better geometrical interpretation than suoervision singals proposed before this paper.
2. Overview of many recent face recognition modes and loss functions
3. Release the cleaned training data(MS-Celeb-1M，MegaFace FaceScrub)

![](https://i.imgur.com/OF8gBQx.png)

## From Softmax to ArcFace

### Softmax:

Drawback: could not explicitly optimize the feature embedding to enforce higher similarity for intra-class samples and diversity for inter-class samples, which results in a performance gap.

![](https://i.imgur.com/Gu8NvTC.png)

### Weights Normalization:

Make the predictions only depend on the angle between the feature and the weight.

![](https://i.imgur.com/YETxEvo.png)

### Multiplicative Angular Margin:

enhance the intra-class compactness and inter-class discrepancy

![](https://i.imgur.com/6JeSbDK.png)

### Softmax v.s. ArcFacethe 

- softmax loss provides roughly separable feature embedding but produces noticeable ambiguity in decision boundaries.
- ArcFace loss can obviously enforce a more evident gap between the nearest classes.

![](https://i.imgur.com/8fbuOEz.png)

## Comparison with SphereFace and CosFace

![](https://i.imgur.com/ziUUX0Q.png)

## Other losses

### Intra-Loss 

improve the intra-class compact- ness by decreasing the angle/arc between the sample and the ground truth centre.

![](https://i.imgur.com/JEG8rFh.png)

### Inter-Loss

enhance inter-class discrepancy by increasing the angle/arc between different centres.

![](https://i.imgur.com/oJUs7fH.png)

### Triplet-Loss

aims at enlarging the angle/arc margin between triplet samples. 

