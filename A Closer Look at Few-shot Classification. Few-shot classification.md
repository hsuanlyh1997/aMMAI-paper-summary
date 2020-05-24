A Closer Look at Few-shot Classification. 
===
*Chen, Wei-Yu, et al., ICLR 2019*

This paper is about Few-shot Classification.

## Introduction
### Few-shot Classification
learning to generalize to unseen classes during training
### Limitation
the discrepancy of the implementation details and lack of domain shift between the base and novel classes


## Contribution
- a unified testbed for several different few-shot classification algorithms for a fair comparison, and the results show that deeper backbones significantly reduce the performance gap among methods on datasets with limited domain differences
- a baseline method with a distance-based classifier surprisingly achieves competitive performance with the SOTA meta-learning methods on both mini-ImageNet and CUB datasets
- Investigate a practical experimental setting for evaluating the cross-domain generalization ability for few-shot classification algorithms

## Overview of Few-shot Classification Algorithms
### Baseline/Baseline++
![](https://i.imgur.com/er1nKgX.png)
### Meta-learning Algorithms
![](https://i.imgur.com/DpBx3v8.png)

## Results
### Datasets and scenarios:
1. Generic object recognition(mini-ImageNet)
2. Fine-grained image classification(CUB-200–2011)
3. Cross-domain adaptation(mini-ImageNet->CUB)

### Evaluation
- Reduce intra-class variation is an important factor in the current few-shot classification problem setting
![](https://i.imgur.com/aM6J1NL.png)

- Deeper backbone reduces the gap among different methods
![](https://i.imgur.com/eRQ3aVc.png)

- When the domain difference grows larger, the adaptation based on a few novel class instances becomes more important.
![](https://i.imgur.com/5tGlqxQ.png)

## Conclusion
- the Baseline++ model is competitive to SOTA under standard conditions, and the Baseline model achieves competitive performance with recent SOTA meta-learning algorithms on both CUB and mini-ImageNet benchmark datasets when using a deeper feature backbone 
- the Baseline compares favorably against all the evaluated meta-learning algorithms under a realistic scenario where there exists domain shift between the base and novel classes.
