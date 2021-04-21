## Objectives

- Understand the definition of clustering
- Understand clustering cost with different similarity measures
- Understand the K-means algorithm

### Partition Definition

A partition of a set is a grouping of the set's elements into non-empty subsets, in such a way that every element is included in one and only one of the subsets. In other words, 𝐶1,𝐶2,...,𝐶𝐾 is a partition of {1,2,...,𝑛} if and only if

𝐶1∪𝐶2∪...∪𝐶𝐾={1,2,...,𝑛}
and
𝐶𝑖∩𝐶𝑗=∅for any 𝑖≠𝑗 in {1,...,𝑘} 
 
(Union of all 𝐶𝑗's is the original set and the intersection of any 𝐶𝑖 and 𝐶𝑗 is an empty set.)

For example,

{3},{1},{2}, 
{2,1},{3},
{2,3,1}
 
are all partitions of the set {1,2,3}.

### K-Means Algorithm

*K-Means with distance metric does not scale well with increasing dimensinos. Distance-based similarity measure converges to a constant value between any given examples. [wikipedia - curse of dimensionality](https://en.wikipedia.org/wiki/Curse_of_dimensionality#Distance_functions)*



