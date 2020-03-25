# VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection

*Zhou, Yin, and Oncel Tuzel. CVPR 2018*

## Objective

An end-to-end trainable network using only raw point cloud data to predict 3D bounding boxes.

![VoxelNet directly operates on the raw point cloud (no need for feature engineering) and produces the 3D detection re- sults using a single end-to-end trainable network.](https://i.imgur.com/ZuqDZu8.png)

## Contribution

- Propose an **end-to-end** point-cloud-based 3D object detection network.

- Present an efficient method for VoxelNet implementation.

- VoxelNet produces SOTA results in LiDAR-based car, pedestrian, and cyclist detection benchmarks.

##VoxelNet

Subdivide the 3D point cloud space into voxels and transform randomly-sampled points within each voxel to a vector representaion through Voxel Feature Encoding(VFE) layer. Then, process the sparse 4D tensor to aggregate spatial context by 3D Convolutional Middle Layers. Lastly, using Region Proposal Network to generate the 3D detection.

![VoxelNet architecture](https://i.imgur.com/mKZNkZf.png)

### Feature learning network

Stacking VFE layers encode point interactions within a voxel and allows the final feature representation to learn descriptive shape information.

**Voxel Feature Encoding(VFE) layer**

Raw 3D points are firstly transformed into the feature space through the fully connected network to obtain the point-wise features. Then, use element-wise max pooling to get local aggregated features. Finally, combine point-wise feature with locally aggregated feature.

![Voxel feature encoding layer](https://i.imgur.com/SWq5DSy.png)

### Convolutional middle layers

The convolutional middle layer aggregate voxel-wise features within a progressively expanding receptive field, adding more context to the shape description. 

### Region proposal network

The RPN is fed with feature maps from convolutional middle layers and the learning targets are a probability score map and a regression map. A technique of multi-scale feature aggregation is used to fuse high level and low level feature. 

![](https://i.imgur.com/4JiNw7d.png)

## Efficient Implementation

Since the points are sparsely distributed across space and each voxel has a variable number of points, a hash table is used to efficiently look up the voxel corrdinate.

![](https://i.imgur.com/r1R2ajg.png)

