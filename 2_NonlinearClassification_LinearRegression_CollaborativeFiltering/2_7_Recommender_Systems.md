## Objectives

At the end of this lecture, you will be able to

understand the problem definition and assumptions of recommender systems

understand the impact of similarity measures in the K-Nearest Neighbor method

understand the need to impose the low rank assumption in collaborative filtering

iteratively find values of  𝑈  and  𝑉  (given  𝑋=𝑈𝑉𝑇 ) in collaborative filtering


## Introduction

- Problem definition
- K-Nearest Neighbor Method (KNN)
- Matrix factorization

## K-Nearest Neighbor Method

Our goal in the movie recommender system problem is to predict the movie ranking that a user would give on a movie that (s)he has not seen.

Let  𝑚  be the number of movies and  𝑛  the number of users. The ranking  𝑌𝑎𝑖  of a movie  𝑖∈{1,...,𝑚}  by a user  𝑎∈{1,...,𝑛}  may already exist or not. Our goal is to predict  𝑌𝑎𝑖  in the case when  𝑌𝑎𝑖  does not exist.

**𝐾 -Nearest Neighbour**
The  𝐾 -Nearest Neighbor method makes use of ratings by  𝐾  other “similar" users when predicting  𝑌𝑎𝑖 .

Let  KNN(𝑎)  be the set of  𝐾  users “similar to" user  𝑎 , and let  sim(𝑎,𝑏)  be a similarity measure between users  𝑎  and  𝑏∈KNN(𝑎) . The  𝐾 -Nearest Neighbor method predicts a ranking  𝑌𝑎𝑖  to be :

𝑌ˆ𝑎𝑖=∑𝑏∈KNN(𝑎)sim(𝑎,𝑏)𝑌𝑏𝑖∑𝑏∈KNN(𝑎)sim(𝑎,𝑏). 
 
The similarity measure  sim(𝑎,𝑏)  could be any distance function between the feature vectors  𝑥𝑎  and  𝑥𝑏  of users  𝑎  and  𝑏 , e.g. the euclidean distance  ‖𝑥𝑎−𝑥𝑏‖  and the cosine similarity  cos𝜃=𝑥𝑎⋅𝑥𝑏‖𝑥𝑎‖‖𝑥𝑏‖ . We will use these similarity measures again in Unit 4 Unsupervised Learning.

A drawback of this method is that the success of the  𝐾 -Nearest Neighbor method depends heavily on the choice of the similarity measure. In the next section, we will discuss collaborative filtering, which will free us from the need to define a good similarity measure.

## Collaborative Filtering with Matrix Factorization
*Matrix X is a user movie score matrix*
Assumption: Matrix X is low rank
Rank: intutively means categories of movies

We now use collaborative filtering to solve the movie recommender system problem.

As we saw in the previous problem, we ended up with an unsatisfactory and trivial solution of  𝑋  by minimizing the objective alone:

𝐽(𝑋)=∑𝑎,𝑖∈𝐷(𝑌𝑎𝑖−𝑋𝑎𝑖)22+𝜆2∑(𝑎,𝑖)𝑋2𝑎𝑖. 
 
In the collaborative filtering approach, we impose an additional constraint on  𝑋 :

𝑋=𝑈𝑉(T) 
 
for some  𝑛×𝑑  matrix  𝑈  and  𝑑×𝑚  matrix  𝑉𝑇 . The number  𝑑  is the rank of the matrix  𝑋 .

