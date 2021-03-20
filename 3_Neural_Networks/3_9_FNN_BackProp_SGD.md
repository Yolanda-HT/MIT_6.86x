## Objectives

Feedforward Neural Networks, Back-propagation, and Stochastic Gradient Descent At the end of this lecture, you will be able to

- Write down **recursive relations** with **back-propagation** algorithm to compute the gradient of the loss function with respect to the weight parameters.

- Use the **stochastic descent algorithm** to train a feedforward neural network.

- Understand that it is not guaranteed to reach global (only local) optimum with SGD to minimize the training loss.

- Recognize when a network has **overcapacity**.


## Back propagatino

*[Jacobian matrix](https://en.wikipedia.org/wiki/Jacobian_matrix_and_determinant)*


Once we set up the architecture of our (feedforward) neural network, our goal will be to find weight parameters that minimize our loss function. We will use the stochastic gradient descent algorithm (which you learned in Lecture 4 and revisited in lecture 5) to carry out the optimization.

This involves computing the gradient of the loss function with respect to the weight parameters.

Since the loss function is a long chain of compositions of activation functions with the weight parameters entering at different stages, we will break down the computation of the gradient into different pieces via the chain rule; this way of computing the gradient is called the back-propagation algorithm.

In the following problems, we will explore the main step in the stochastic gradient descent algorithm for training the following simple neural network from the video:


This simple neural network is made up of  𝐿 hidden layers, but each layer consists of only one unit, and each unit has activation function  𝑓 .
As usual,  𝑥  is the input,  𝑧𝑖  is the weighted combination of the inputs to the  𝑖𝑡ℎ  hidden layer. In this one-dimensional case, weighted combination reduces to products:

 	 𝑧1 	 = 	 𝑥𝑤1 	 	 
 	 for 𝑖=2…𝐿:𝑧𝑖 	 = 	 𝑓𝑖−1𝑤𝑖
 	 where 𝑓𝑖−1=𝑓(𝑧𝑖−1). 	 	 
We will use the following loss function:

 	 (𝑦,𝑓𝐿)=(𝑦−𝑓𝐿)2 	 	 
where  𝑦  is the true value, and  𝑓𝐿  is the output of the neural network.