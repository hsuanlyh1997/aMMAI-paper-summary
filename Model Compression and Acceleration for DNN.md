Model Compression and Acceleration for Deep Neural Networks
===
*Cheng, Yu, et al., IEEE Signal Processing Magazine*

This paper is a survey of different approaches for model compression and acceleration in deep neural network


![](https://i.imgur.com/xfbgu4G.png)

## Parameter pruning and sharing
![](https://i.imgur.com/tMlsNTB.png)
### Quantization and binarization
Network quantization compresses the original network by reducing the number of bits required to represent each weight
#### Drawbacks
- The accuracy of such binary nets is significantly lowered when dealing with large CNNs such as GoogleNet
- These binary nets is that existing binarization schemes are based on simple matrix approximations and ignore the effect of binarization on the accuracy loss

### Pruning and sharing
Used to reduce network complexity and to address the overfitting issue
#### Drawbacks
- Pruning with l1 or l2 regularization requires more iterations to converge
- All pruning criteria require manual setup of sensitivity for layers, which demands fine-tuning of the parameters and could be cumbersome for some applications

### Designing the structural matrix
An m x n matrix that can be described using much fewer parameters than mn is called a *structured* matrix. The structure should not only reduce the memory cost but also dramatically accelerate the inference and training stage via fast matrix-vector multiplication and gradient computations
#### Drawbacks
- The structural constraint will cause loss in accuracy since the constraint might bring bias to the model
- How to find a proper structural matrix is difficult and there is no theoretical way from which to derive it

### Low-rank factorization
![](https://i.imgur.com/dMgUNSh.png)
![](https://i.imgur.com/J1Zmwf7.png)

- Since there might be a significant amount of redundancy in the tensor, tensor decomposition seems to be a particularly promising way to remove the redundancy. Regarding to the fully connected layer, it can be viewed as a two-dimensional (2-D) matrix and the low-rankness can also help
- Low-rank approaches complement recent advances in deep learning such as dropout, rectified units, and maxout

#### Drawbacks
- The implementation is not that easy since it involves a decomposition operation, which is computationally expensive
- Current methods perform low-rank approximation layer by layer, and thus cannot perform global parameter compression, which is important as different layers hold different information
- Factorization requires extensive model retraining to achieve convergence when compared to the original model.

### Transferred/compact convolutional filters
![](https://i.imgur.com/paKr74r.png)
![](https://i.imgur.com/YS0lq4D.png)

#### Drawbacks
- These methods can achieve competitive performance for wide/flat architectures (like VGGNet) but not narrow/special ones (like GoogleNet and ResNet)
- The transfer assumptions sometimes are too strong to guide the algorithm, making the results unstable on some data sets

### Knowledge distillation (KD)
#### Drawbacks
- Can only be applied to classification tasks with softmax loss function, which hinders its usage
- The model assumptions sometimes are too strict to make the performance competitive with other types of approaches

## Benchmarks, evaluation, and databases
![](https://i.imgur.com/iqhqRus.png)
