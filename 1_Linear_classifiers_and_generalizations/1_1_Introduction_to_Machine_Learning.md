# Linear Classifiers and Generalizations

## Objectives

Introduction to Machine Learning

At the end of this lecture, you will be able to

- understand the goal of machine learning from a movie recommender example

- understand elements of supervised learning, and the difference between the training set and the test set

- understand the difference of classification and regression - two representative kinds of supervised learning

## What is machine learning

Machine learning as a discipline aims to design, understand, and apply computer programs that learn from experience (i.e. data) for the purpose of modelling, prediction, and control. We will start with prediction as a core machine learning task.

There are many types of predictions that we can make. We can predict outcomes of events that occur in the future such as the market, weather tomorrow, the next word a text message user will type, or anticipate pedestrian behavior in self driving vehicles, and so on.

We can also try to predict properties that we do not yet know. For example, properties of materials such as whether a chemical is soluble in water, what the object is in an image, what an English sentence translates to in Hindi, whether a product review carries positive sentiment, and so on.


## Supervised learning

Common to all these “prediction problems" mentioned on the previously is that it is very hard to write down a solution in terms of rules or code directly, and far easier to provide examples of correct behavior. For example, how would you encode rules for translation, or image classification? It is much easier to provide large numbers of translated sentences, or examples of what the objects are on a large set of images. The ability to learn the solution from examples is what has made machine learning so popular and pervasive.

We will start with supervised learning in this course. In supervised learning, we are given an example (e.g. an image) along with a target (e.g. what object is in the image), and the goal of the machine learning algorithm is to find out how to produce the target from the example.

More specifically, in supervised learning, we hypothesize a collection of functions (or mappings) parametrized by a parameter, from the examples (e.g. the images) to the targets (e.g. the objects in the images). The machine learning algorithm then automates the process of finding the parameter of the function that fits with the example-target pairs the best.

### Classifier

Training data can be graphically depicted on a (hyper)plane. Classifiers are mappings that take feature vectors as input and produce labels as output. A common kind of classifier is the linear classifier, which linearly divides space(the (hyper)plane where training data lies) into two. Given a point  𝑥  in the space, the classifier  ℎ  outputs  ℎ(𝑥)=1  or  ℎ(𝑥)=−1 , depending on where the point  𝑥  exists in among the two linearly divided spaces.

### Classification v.s. regression

Classification maps feature vectors to categories. The number of categories need not be two - they can be as many as needed. Regression maps feature vectors to real numbers. There are other kinds of supervised learning as well.

For a more thorough statistical background on classification and regression, please check out the following links. [Classification Regression](https://en.wikipedia.org/wiki/Regression_analysis)





