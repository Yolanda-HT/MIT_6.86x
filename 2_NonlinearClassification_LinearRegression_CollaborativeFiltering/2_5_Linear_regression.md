## Objectives

Linear Regression

At the end of this lecture, you will be able to

- write the training error as least squares criterion for linear regression

- use stochastic gradient descent for fitting linear regression models

- solve closed-form linear regression solution

- identify regularization term and how it changes the solution, generalization


## Overview

- Learning algorithms
	- Gradient based
	- Close form

- Regularization
	- Noisy data
	- Not enough training data

## Emppirical Risk
- Empirical risk is the average of loss
	- *[Wikipedia: Empirical risk minimization](https://en.wikipedia.org/wiki/Empirical_risk_minimization)*

- Two types of mistakes:
	- Structural mistakes: Linear function is not sufficient for training data
	- Estimation mistakes: Limited training data (the more parameters, the higher requirement for training data)

## Error decomposition and the bias-variance trade-off
In the lecture, we intuitively defined the structural and estimation mistakes. Here we provide a more formal definition of these ideas for a regression problem.

Suppose we want to learn the relationship between random variables  𝑥∈ℝ𝑑  and  𝑦∈ℝ , where the ground truth relationship is  𝑦=𝑓(𝑥) . Of course  𝑓  is unknown to us, but we observe a training set  (𝑥1,𝑦1) ,  (𝑥2,𝑦2) , ...,  (𝑥𝑛,𝑦𝑛)  and we hope to find a function  𝑓̂   to approximate the true funtion  𝑓 .

However, our observed data might not be  100%  accurate as there can be many kinds of noise and uncertainty containing in the data. Thus, we further assume a random noise variable  𝜖  is added on top of  𝑦 :

𝑦=𝑓(𝑥)+𝜖 
 
where  𝜖∼(0,𝜎2) 

We learned from the lecture that we can find  𝑓̂   by minimizing the empirical risk on the training set. As we know the training set is a random observation of the underlying relationship and contains noise, different training set will give us different estimator  𝑓̂ (𝑥) . Hence, we can define  𝔼[𝑓̂ (𝑥)]  to be the expected estimator over all possible training sets.

Now let's look at when we have a new  𝑥  with unknown  𝑦 , what is the expected prediction error looks like for our estimator given all possible training sets:

 	 𝔼[(𝑦−𝑓̂ (𝑥))2] 	 =𝔼[(𝑓(𝑥)+𝜖−𝑓̂ (𝑥))2] 	 	 
 	 	 =(𝑓(𝑥)−𝔼[𝑓̂ (𝑥)])2+𝔼[(𝑓̂ (𝑥)−𝔼[𝑓̂ (𝑥)])2]+𝔼[𝜖2] 	 	 
We skip some derivations of this result, can you get this result on your own?

As we can see, there are three terms in this error decomposition:

The first term is the square of the difference between the true  𝑓(𝑥)  and the expected estimation over all possible training sets. This term is usually called bias and it describes how much the average estimator fitted over all datasets deviates from the underlying true  𝑓(𝑥) . This corresponds to the structural mistake in the lecture.

The second term is the variance of the estimator (recall variance definition in statistics). It describes on average how much a single estimator deviates from the expected estimator over all data sets. This corresponds to the estimation error in the lecture.

The third term  𝔼[𝜖2]=𝜎2  is the error from the inherent noise of the data and we can do nothing to minimize it, thus it is sometimes called irreducible error. The irreducible error gives a lower bound on the expected prediction error.

Question for you to think: Apparently, the empricial risk is just an approximation of the true risk (i.e.  𝔼[(𝑓(𝑥)−𝑓̂ (𝑥))2] ). If we were able to learn the model by minimizing the true risk, which part of the error decomposition will become 0?

The task of supervised learning is to reduce the bias and variance at the same time, but because of the noise in the training data, it is not possible to simultaneously minimize these two sources of errors. This is known as the **bias-variance trade-off**.


To reduce bias, we can assume a more complex hypothesis space and fit a more powerful model. The model will be able to fit even the noise in the training set. However, this increases the error from variance because given another training set, the randomness of the noise will results in a very different model. This situation is often called 'overfitting'. On the other hand, we can have a more simple model to reduce the variance, but this can make the bias very large. For example, in the extreme case, let our model be  𝑓̂ (𝑥)=𝑐 , where  𝑐  is a constant. This will give us  0  variance but you can imagine it can hardly make any correct predictions. This situation is known as 'underfitting'.

In a few pages, you will see how regularization can be used to restrict the complexity for linear regression so that we will be able to search for a sweet spot where the total error from variance and bias is the minimum.

## Gradient Based Approach

## Closed form solution





