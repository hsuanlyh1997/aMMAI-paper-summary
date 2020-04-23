Robust Sparse Coding for Face Recognition
===
*Yang et al, CVPR 2011*

## Introduction
A sparse coding model assumes that the coding residual 𝒆 = 𝒚−𝐷𝜶 follows Gaussian or Laplacian distribution, but the assumption may not be hold when the observation 𝒚 is noisy or occlusions, corruptions and expression variations occur in the query face images.

## Robust Sparse Coding

### Distribution induced weights
<img src="https://i.imgur.com/LLpg1Dx.png" width=250>
So, first order Taylor expansion in the neighborhood of
<img src="https://i.imgur.com/YTE17n9.png" width=400>
In sparse coding, it is usually expected that the fidelity term is strictly convex. So we approximate the residual term as <img src="https://i.imgur.com/kVeAyU9.png" width=250>
Since 𝒆 = 𝒚 − 𝐷, the RSC model can be approximated by <img src="https://i.imgur.com/G4ET20q.png" width=300>, which is a weighted LASSO problem.
Then, since Each 𝑊𝑖,𝑖$ is a non-negative scalar, so the weighted LASSO in each iteration is a convex problem, which could be solved easily by methods such as 𝑙1-ls 

#### Weighted Function
<img src="https://i.imgur.com/MMzJIHK.png" width=500>

### Iteratively Reweighted Sparse Coding
<img src="https://i.imgur.com/VeAGV87.png" width=500>

#### Complexity
The computational complexity of our proposed RSC is 𝑂(𝑘(𝑚)𝜀), where 𝑘 is the number of iteration, and 𝑘 depends on the percentage of outliers in the face image.

## Experimental Results
### Without Occlusion
![](https://i.imgur.com/EJ9cthG.png)
![](https://i.imgur.com/maiENbs.png)
### With Occlusion
![](https://i.imgur.com/xcpqap0.png)
![](https://i.imgur.com/6yFMY1i.png)

#### FR with real face disguise
![](https://i.imgur.com/MMTzWkE.png)

## Conclusion
Pixel-level importance measure and seeking for an MLE (maximum likelihood estimation) solution of the sparse coding problem makes RSC robustness to various types of outliers (i.e., occlusion, corruption, expression, etc.)


