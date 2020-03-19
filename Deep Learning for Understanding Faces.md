# Deep Learning for Understanding Faces

*Ranjan et al., “Deep Learning for Understanding Faces: Machines May Be Just as Good, or Better, than Humans”. IEEE Signal Processing Magazine 2018.*

## Introduction

An overview of deep learning methods applied in face recognition. 

### An automatic face recognition system should contain:

1. Face detector: localize faces in images or videos.
2. Fiducial point detector: localize crucial facial key-points.
3. Feature descriptor: extract disentangled face feature.

## Face detection in unconstrained images

### Region based 

- generate a pool of generic object-proposals.
- use DCNN to classify whether or not a given proposal contains a face.

**Faster R-CNN**

**Drawback:** 

1. difficult faces are hard to capture in any object proposal, which results in a low recall. 

2. the additional proposal generation task increases the overall computation time.

### Sliding-window based 

- computes a face detection score and bounding-box coordinates at every location in a feature map at a given scale.
- different scales detections are typically carried out by creating an image pyramid at multiple scales.

**DP2MFD and DDFD**

### Single-shot detector(SSD)

- A sliding-window-based detector while utilizing the inbuilt pyramid structure present in DCNNs. 

## Finding crucial facial keypoints and head orientation

### Model based

**AAM, ASM, and CLM**, learn a shape model during training and use it to fit new faces aduring testing. 

### Cascaded regression based

learn a model that directly maps the image appearance to the target output.

## Face identification and verification

![a general pipeline for training and testing a face identification/verification system using DCNNs](https://i.imgur.com/wseDqSa.png)

1. robust face representation.
2. a discriminative classification model (face identification) or similarity measure (face verification).

### Robust feature learning for faces using deep learning

Learning invariant and discriminative feature representations is a critical step in a face recognition system.

**DeepFace, DeepID frameworks, FaceNet**

### Discriminative metric learning for faces

- Learning a classifier or a similarity measure from data is another key component for improving the performance of a face recognition system.
- exploit the label information from face images or face pairs.

## Facial Attributes

From a single face, we are able to identify facial attributes such as gender, expression, age, skin tone, etc.

![A sample pipeline of a face attribute detection algorithm for mobile authentication [98]. CNNAA: CNN for Facial Attribute-Based Active Authentication.](https://i.imgur.com/8MWA0iS.jpg)

## Open issues

-  **Face detection**: 

  - the wide range of variations in the appearance of faces caused mainly by changes in illumination, facial expression, viewpoints, occlusions, etc. 

  - blur and low resolution challenge the face detection task.

- **Fiducial detection**: 

  - most face datasets are small, hard to make the face alignment system robust to the challenges, including extreme pose, low illumination, and small, blurry face images. 

  - It has not yet been thoroughly studied which layers exactly correspond to local features for fiducial detection.

- **Face identification/verification**: 

  - memory constraints limited by graphics cards, how to choose informative pairs or triplets and train the network end to end using online methods on large-scale data sets is still an open problem.
  - to incorporate full motion video processing in deep networks for enabling video-based face analytics.

