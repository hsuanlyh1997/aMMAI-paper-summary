# A Survey on Learning to Hash

*Jingdong Wang, Ting Zhang, Jingkuan Song, Nicu Sebe, and Heng Tao Shen. TPAMI, 2017*

## Introduction
### Hashing algorithms
- Locality sensitive hashing (LSH): data-independent
- **Learning to hash: data-dependent**
### The main methodology of learning to hash is similarity preserving
- pairwise similarity preserving
- multiwise similarity preserving
- implicit similarity preserving
- quantization

## Learning to hash
Learn a **hash function y = h(x)**
Goals: 

1. good search accuracy
2. search efficiently

### Hash Function
- linear hash function
- kernel function
- non-parametric function

### Similarity
#### Distance between hash codes
- Euclidean distance
- Hamming distance/similarity

### Loss Function
preserve the similarity order

### Optimization
#### problem
1. handle the sgn function, which leads to a challenging mixed-binary-integer optimization problem
2. high time complexity when processing largescale data

### Categorization
based on similarity preserving: pairwise, multiwise, implicit, and quantization

## pairwise similarity preserving

### Similarity-distance product minimization (SDPM) 
The distance in the coding space is expected to be smaller if the similarity in the original space is larger. 
### Similarity-similarity product maximization (SSPM)
The similarity in the coding space is expected to be larger if the similarity in the original space is larger.
### Distance-distance product maximization (DDPM)
The distance in the coding space is expected to be larger if the distance in the original space is larger.
### Distance-similarity product minimization (DSPM) 
The similarity in the coding space is expected to be smaller if the distance in the original space is larger.
### Similarity-similarity difference minimization (SSDM)
The difference between the similarities is expected to be as small as possible.
### Distance-distance difference minimization (DDDM) 
The difference between the distances should be as small as possible.
### Normalized similarity-similarity divergence minimization (NSSDM) 

## multiwise similarity preserving
maximizing the agreement of the similarity orders over more than two items computed from the input space and the coding space
* Order preserving hashing
## implicit similarity preserving
pursuing effective space partitioning without explicitly evaluating the relation between the distances/similarities in the input and coding spaces. 

method: partition the space, formulated as a classification problem, with the maximum margin criterion or the code balance condition.
## quantization
quantization can be derived from the distance-distance difference minimization criterion

