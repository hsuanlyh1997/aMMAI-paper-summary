“Why Should I Trust You?”: Explaining the Predictions of Any Classifier
===
*Ribeiro, et al., KDD 2016*

## Motivation
Thanks to deep models such as DNN, the performance of many tasks has been improved, but model are still unexplainable. The models trained by deep learning seem to be completely a "black box". In many scenarios, if the model is not interpretable, it cannot be applied at all(ex. medicine, lawyers). Therefore, the authors wanted to propose a model-independent interpretation model for explaining the output of "black boxes".

## Contribution
- Proposed an algorithm *LIME* that can explain the predictions of any classifier or regressor in a faithful way by approximating it locally with an interpretable model.
- Proposed a method *SP-LIME* that selects a set of representative instances with explanations to address the “trusting the model” problem, via submodular optimization.
- Comprehensive evaluation with simulated and human subjects, where the authors measure the impact of explanations on trust and associated tasks. 

## The case of explainantion
**explaining a prediction**
present textual or visual artifacts that provide qualitative understanding of the relationship between the instance’s components (e.g. words in text, patches in an image) and the model’s prediction.
![](https://i.imgur.com/LeHAGXp.png)

### Desired Characteristics for Explainers
- Interpretable 
- Local Fidelity
- Model-Agnostic
- Global Perspective

## Local Interpretable Model-agnostic Expla- nations (LIME)
The overall goal of LIME is to identify an interpretable model over the interpretable representation that is locally faithful to the classifier.
![](https://i.imgur.com/FzXKP4U.png)
The LIME algorithm uses a linear regression algorithm to sample each sample x and the characteristics of other sample z (take some of the features), and use the normalized distance from z to x as the weight of sample z, the closer the distance the greater the weight, and learn a linear regression model.
![](https://i.imgur.com/NnsXF6X.png)

## SP-LIME 
To choose as few samples as possible to cover as many features as possible.
![](https://i.imgur.com/40yppIO.png)

## Experiments
### Simulated user experiments
To evaluate the utility of explanations in trust-related tasks, they addressed the following questions:
1) Are the explanations faithful to the model?
2) Can the explanations aid users in ascertaining trust in predictions?
3) Are the explanations useful for evaluating the model as a whole?

![](https://i.imgur.com/43ssz9e.png)

Limited to select only 10 features, the feature selected by LIME can achieve better results than other methods

![](https://i.imgur.com/EDjzlvL.png)


![](https://i.imgur.com/6lvfOr1.png)

### Evaluation
evaluate LIME and SP-LIME in the following settings: 
1) can users choose which of two classifiers generalizes better?
2) based on the explanations, can users perform feature engineering to improve the model?
3) are users able to identify and describe classifier irregularities by looking at explanations?

![](https://i.imgur.com/m7JdTYQ.png)

![](https://i.imgur.com/BiZNNh1.png)
snow is the key factor


