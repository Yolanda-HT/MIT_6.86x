## Objectives

Linear Classifiers and Perceptron Algorithm

At the end of this lecture, you will be able to

- understand the concepts of Feature vectors and labels, Training set and Test set, Classifier, Training error, Test error, and the Set of classifiers

- derive the mathematical presentation of linear classifiers

- understand the intuitive and formal definition of linear separation

- use the perceptron algorithm with and without offset

### Perceptron algorithm

Perceptron ({(𝑥(𝑖),𝑦(𝑖)),𝑖=1,...,𝑛},𝑇): 
  initialize  𝜃=0 (vector);
    for  𝑡=1,...,𝑇  do
      for  𝑖=1,...,𝑛  do
        if  𝑦(𝑖)(𝜃⋅𝑥(𝑖))≤0  then
        update  𝜃=𝜃+𝑦(𝑖)𝑥(𝑖)