## Objectives

- Understand what Generative Models are and how they work
- Understand estimation and prediction phases of generative models
- Derive a relation connecting generative and discriminative models
- Derive Maximum Likelihood Estimates (MLE) for multinomial and Gaussian generative models


## Generative v.s. Discriminative models

Differences:
- Generative model: explicitely models the actual distribution of each class
- Discriminative model: models the decision boundary between classes

Generative model: 
- Multinomials
- Gaussians

Two questions:
- Estimation: how do we estimate the model
- Prediction: how do we use the model for prediction

## Simple multinomial generative model

Consider a very simple multinomial model 𝑀 to generate text in documents.

Let us assume that this model 𝑀 has a fixed vocabulary 𝑊 and that we generate a document by sampling one word at a time from this vocabulary. Furthermore, all the words that are generated by 𝑀 are independent of each other.

We would like to capture the fact in our generative model 𝑀 that some words in 𝑊 are more likely to occur in any given document than the others. So, the first thing that 𝑀 models is how likely it is to generate certain word 𝑤∈𝑊. We denote this probability by 𝑃(𝑤|𝜃)=𝜃𝑤, where 𝜃𝑤 is a parameter in our model 𝑀.


