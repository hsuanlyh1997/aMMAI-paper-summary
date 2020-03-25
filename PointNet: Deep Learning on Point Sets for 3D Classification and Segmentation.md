# PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation

*Qi, Charles R., et al. CVPR 2017*

## Objective

An end-to-end trainable network using only raw point cloud data to learn point-wise features.

## Properties of Point Sets in $\mathbb R^n$

### Unordered

Point cloud is a set of points without specific order, so a network that consumes $N$ 3D point sets needs to be invariant to $N!$ permutations of the input set in data feeding order.

### Interaction among points

Points are not isolated, and neighboring points form a meaningful subset. Therefore, the model needs to be able to capture local structures from nearby points, and the combinatorial interactions among local structures.

### Invariance under transformations

As a geometric object, the learned representation of the point set should be invariant to certain transformations. For example, rotating and translating points all together should not modify the global point cloud category nor the segmentation of the points.

> Permutation (order) invariance, transformation invariance, point Interactions should be considered when designing the architecture.

## PointNet

![](https://i.imgur.com/C5RQmzA.png)

### Symmetry Function for Unordered Input

They approximate $h$ by a multi-layer perceptron network and $g$ by a composition of a single variable function and a max pooling function. 

![](https://i.imgur.com/ekGWYTw.png)

### Local and Global Information Aggregation

After computing the global point cloud feature vector, we feed it back to per point features by concatenating the global feature with each of the point features. 

Concatenate the global feature with each of the point features and extract new per point features based on the combined point features. Both local and global information are encoded in the new features

### Joint Alignment Network

Keep transformation invariance.

![](https://i.imgur.com/3ZvcQLG.png)



