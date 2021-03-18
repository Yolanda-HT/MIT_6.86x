## Unit 3 )verview
At the end of this unit, you will be able to

- Implement a feedforward neural networks from scratch to perform image classification task.

- Write down the gradient of the loss function with respect to the weight parameters using back-propagation algorithm and use SGD to train neural networks.

- Understand that Recurrent Neural Networks (RNNs) and long short-term memory (LSTM) can be applied in modeling and generating sequences.

- Implement a Convolutional neural networks (CNNs) with machine learning packages.


# Introduction to Feedforward Neural Networks

## Objectives

At the end of this lecture, you will be able to

- Recognize different layers in a feedforward neural network and the number of units in each layer.

- Write down common activation functions such as the hyperbolic tangent function  tanh , and the rectified linear function (ReLU).

- Compute the output of a simple neural network possibly with hidden layers given the weights and activation functions .

- Determine whether data after transformation by some layers is linearly separable, draw decision boundaries given by the weight vectors and use them to help understand the behavior of the network.

## Motivation to Neural Networks

So far, the ways we have performed non-linear classification involve either first mapping  𝑥  explicitly into some feature vectors  𝜙(𝑥),  whose coordinates involve non-linear functions of  𝑥,  or in order to increase computational efficiency, rewriting the decision rule in terms of a chosen kernel, i.e. the dot product of feature vectors, and then using the training data to learn a transformed classification parameter.

However, in both cases, the feature vectors are chosen . They are not learned in order to improve performance of the classification problem at hand.

Neural networks, on the other hand, are models in which the *feature representation is learned jointly with the classifier* to improve classification performance.


## Neural Network Units
A neural network unit is a primitive neural network that consists of only the “input layer", and an output layer with only one output. It is represented pictorially as follows:


A neural network unit computes a non-linear weighted combination of its input:

 	 𝑦̂  	 = 	 𝑓(𝑧)where 𝑧=𝑤0+∑𝑖=1𝑑𝑥𝑖𝑤𝑖 	 	 
where  𝑤𝑖  are numbers called **weights**,  𝑧  is a number and is the weighted sum of the inputs  𝑥𝑖,  and  𝑓  is generally a non-linear function called the **activation function**.

The above equation in vector form is:

 	 𝑦̂  	 = 	 𝑓(𝑧)where 𝑧=𝑤0+𝑥⋅𝑤, 	 	 
where  𝑥=[𝑥1,…,𝑥𝑑]  and  𝑤=[𝑤1,…,𝑤𝑑]𝑇 .


**hyperbolic tangent function** is defined as
 	 tanh(𝑧) 	 = 	 𝑒𝑧−𝑒−𝑧𝑒𝑧+𝑒−𝑧=1−2𝑒2𝑧+1. 	


##  Introduction to Deep Neural Networks
A deep (feedforward) neural network refers to a neural network that contains not only the input and output layers, but also hidden layers in between. For example, below is a deep feedfoward neural network of 2 hidden layers, with each hidden layer consisting of 5 units:


One of the main advantages of deep neural networks is that in many cases, they can learn to extract very complex and sophisticated features from just the raw features presented to them as their input. For instance, in the context of image recognition, neural networks can extract the features that differentiate a cat from a dog based only on the raw pixel data presented to them from images.

The initial few layers of a neural networks typically capture the simpler and smaller features whereas the later layers use information from these low-level features to identify more complex and sophisticated features. 	 

- Loosely motivated by biological neurons, networks
- Adjustable processing units (~ linear classifers)
- Highly parallel, typically organized in layers
- Deep = many transformations (layers) before output






