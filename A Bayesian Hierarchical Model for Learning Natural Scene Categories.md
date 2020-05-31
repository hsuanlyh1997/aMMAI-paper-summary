A Bayesian Hierarchical Model for Learning Natural Scene Categories
===
*Fei Fei Li, CVPR 2005*

This paper is about how to learn and recognize natural scene categories without training set annotation. 

## Contribution
- use intermediate representation (themes) before classifying scenes
- learns the theme distributions as well as the codewords distribution over the themes without supervision
- introduce generative Bayesian hierarchical model for scene categories

## Approach
- model an image as a collection of local patches. Each patch is represented by a codeword from a large vocabulary of codewords.
• modifying Latent Dirichlet Allocation model bu explicitly introducing a category variable for classification 

![](https://i.imgur.com/MHRGEyZ.png)

### Model
![](https://i.imgur.com/07YN1Y8.png)
![](https://i.imgur.com/EHkceH3.png)


#### Classification
Given x, the probability of each scene class would be
![](https://i.imgur.com/SyhqzJn.png)
![](https://i.imgur.com/c0ok112.png)
above equation is not tractable but can use a wide range of approximate inference algorithms for solving it.

#### Learning
- maximize the log likelihood term logp(x|θ, β, c) by estimating the optimal θ and β.
- using variational inference
* EM algorithm 
iterated until the model parameter values converge
![](https://i.imgur.com/4zy2lNy.png)

![](https://i.imgur.com/23RLz5G.png)

#### Codebook formation
![](https://i.imgur.com/bv7FfdY.png)

## Result
![](https://i.imgur.com/i2A5R1b.png)
![](https://i.imgur.com/N7kVX3v.png)
