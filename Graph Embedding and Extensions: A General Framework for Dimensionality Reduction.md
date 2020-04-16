Graph Embedding and Extensions: A General Framework for Dimensionality Reduction
===
*Shuicheng Yan et al., PAMI 2007*

## Introduction
- a survey of dimensionality reduction algorithms under graph embedding formulation
- proposed a new supervised dimensionality reduction algorithm called Marginal Fisher Analysis


## Graph embedding framework
![](https://i.imgur.com/6pymiTM.png)

### Definitions
![](https://i.imgur.com/ZTJcGAy.png)
![](https://i.imgur.com/qdhq21Z.png)


### Graph-preserving criterion
![](https://i.imgur.com/qrNSIxg.png)where d is a constant and B is the constraint matrix defined to avoid a trivial solution of the objective function.

### Linearization
![](https://i.imgur.com/9yl7R3O.png)

- computationally efficient for both projection vector learning and final classification
- performance may degrade in cases with nonlinearly distributed data

### Kernelization
![](https://i.imgur.com/cVgZPTJ.png)

<img src="https://i.imgur.com/s5ZotrC.png" width=200>,
<img src="https://i.imgur.com/qdNJYca.png" width=300>

### Tensorization
- the extracted feature from an object may contain higher-order structure
- reduce feature dimension
    - avoids the curse of dimensionality issue
    - reduce computational cost

## Previous methods
- PCA
- LDA
- ISODMAP
- LLE and LEA
- Laplacian Eigenmap
![](https://i.imgur.com/bptUu13.png)

## Marginal Fisher Analysis

LDA's limitation: the separability cannot be well characterized without the assumption that the data of each class is of a Gaussian distribution. 

**Marginal Fisher Analysis (MFA)** 
- intrinsic graph for intraclass compactness
- penalty graph for interclass separability

![](https://i.imgur.com/u3Ibv9e.png)


### algorithm procedure:
<img src="https://i.imgur.com/Olf71Uz.png" width=400>
<img src="https://i.imgur.com/pa3uHNN.png" width=400>

### advantage:
- greater projection direction 
- no data distribution assumption needed

## Experiments
![](https://i.imgur.com/dplwfh5.png)
