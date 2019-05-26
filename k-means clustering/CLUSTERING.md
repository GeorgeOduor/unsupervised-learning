
<div id ="top"></div>

______

# <center>Introduction to Clustering with K-Means.</center>
______

### Contents.

1. [What is Clustering](#1)
1. [What is a Cluster?](#2)
1. [Difference between clustering and classification.](#3)
    1. [Uses of Clustering in different industries.](#3.1)
    1. [Why clustering?](#3.2)
1. [Clustering algorithms.](#4)
1. [K- Means Clustering.](#5)
    1. [A little bit of the mathematical side.](#5.1)
    1. [The K-Mean Algorithm](#5.2)
    1. [K-Means Accuracy.](#5.3)
    1. [K-Means Accuracy.](#5.4)
    

<div id ="1"></div>

## What is Clustering?

Clustering means finding clusters in a dataset unsupervised.Unsupervised in this case means that there are no predictor and response variables.

<div id ="2"></div>

## What is a Cluster?

A cluster is a group of objects that are __similar to other objects__ in the cluster and __dissimilar to data points__ in other clusters.

When observations are clustered in a particular dataset,they are partitioned into distinct groups in such a way that the observations within each group are very similar to each other.

<div id ="3"></div>

## Difference between clustering and classification.

Classification predict categorical class labels which means assigning instances to predefined clases in a supervised model while clusteringsimply groups similar observations together in an unsupervised fasion.


<div id ="3.1"></div>

### Uses of Clustering in different industries.

- **Retail/Marketing**

    - Identifying buying paterns of customers.
    
    - Recommending new books or movies to new customers.
    
- **Banking**:
    
    - Fraud detection in credit card use
    
    - Identifying clusters of customers 
    
- **Insurance**:
    
    - Fraud detection in claims analysis.
    
    - Insurance risk of cudtomers.
    
- **Publication**:
    
    - Auto-categorizing news based on their content
    
    - Recomending similar news articles
    
- **Medicine**:

    - Characterising patient behaviour 
    
- **Biology**:
    
    - Clustering genetic markers to identify family ties.
    
 <div id ="3.2"></div>
    
### Why clustering?

In data analysis we can make use of clustering to achieve the following:
    
- Exploratory data analysis.
    
- Summary Generation.
    
- Outlier detection.
    
- Finding duplicates
    
- Pre-procesing step.

<div id ="4"></div>
    
## Clustering algorithms.

Clustering is so popular in many fields and below are some of the clustering algorithms.

1. Partition Based Algorithms:

1. Hierarchical clustering:

1. Density Based algorithm

1. K- Means Clustering.

In this article i am talking about Kmeans algorithm.

<div id ="5"></div>

## K- Means Clustering.

<div id ="5.1"></div>

### A little bit of the mathematical side.

Lets say we have sets, $C_1,C_2,C_3,...,C_K$ that denote indices of the observations in each cluster and must satisfy the following conditions,

1. $C_1 \cup C_2 \cup C_3 \cup ...\cup C_K=\{1,...,n\}$

meaning that each observation must belong to each group.

2. $C_k\cap C_{k'}=\varnothing \    \forall \ k \neq k'$

meaning that there is no overlaping among the groups.

The idea is that clustering a good cluster is one for which the within luster variation is as small as possible.

Having a measure $W(C_k)$  representing the amount of variation within the cluster,below is the problem problem that it gives and requires solution.

$$minimize\{\sum_{k=1}^KW(C_k)\};C_1,C_2,C_3,...,C_K$$

A first thought of solving this is to calculate the distance between two observations using the eulcledian distance.The euclidian distace can be calculated as follows:

$$Dis(x_1,x_2) = \sqrt{\sum_{i=0}^n(x_{1i}-x_{2i})^2}$$

In case of many variables the same equation is used in a hire dimension.
By the use of Eulidien distance ,we can then define the within cluster variation as:

$$W(C_k)=\frac{1}{|C_k|}\sum _{i,i'\in C_k }\sum_{j=1}^p(x_{ij}-x_{i'j})^2$$

In the above function $|C_k|$ stands for the number of observationsin the k$^{th}$ cluster.

Normalization in this case is a requirent to get the correct disimilarity measure but is higly depends on on the data type and also the domain that clustering is done for it.

The two equations above combines to give;

$$minimize\{\frac{1}{|C_k|}\sum _{i,i'\in C_k }\sum_{j=1}^p(x_{ij}-x_{i'j})^2\};C_1,C_2,C_3,...,C_K$$

From here the task is to find an algorithm that will partition the observations into K clusters such that the above objective is met.

In simple terms we can say that K-Means tries to minimize the _intra-cluster(within)_$Dis(x_1,x_2)$ class distances while trying to maximize the _inter-cluster(between)_$Dis(C_1,C_2)$ class distances.

Error per cluster can be calculted as:
$$SSE = \sum_i^n(x_i-C_j)^2$$

<div id ="5.2"></div>

### The K-Mean Algorithm

Bellow is an algorithm that can be used to solve the k means problem:

1. Choose a number of clusters "K"

1. Randomly assign each point to a cluster

1. Until clusters stop changing,repeat the following:

    - For each cluster,compute the cluster centroid by taking the mean vector of points in the cluster.
    
    - Assign each data point to the cluster for which the centroid is closest.

<div id ="5.3"></div>    

### K-Means Accuracy.

How do we evaluate the K means model?We can do this by following two approches:

1. **External Aproach**: In this case we compare the clusters with the ground truthif available.Unfortunately this is absent in the real world.

1. **Internal Approach:** In this the average distance of data points within a cluster.Also average of the data points distance from the cluster centroids can be used as a metric.

<div id ="5.4"></div>

### Choosing the Value of K.

There is no straightforward way of choosing the best value .On of the methods that can be used to run the clustering across the different values of K and looking at a metric of accuracy for clustering eg the average distance of datapoints from their cluster centroid.This shows how dense or spece a cluster was.

The problem with this is only that the distance of the datapoints will always reduce as the value of K increases.

Therefor inorder to get the best value of K,the metric is ploted against the different values of K and the point where the metric sharply shifts is determined.This is called the __elbow method.__


[Back to top](#top)

____
## <center>Python Implementation</center>
___

After uderstanding K-Means Clustering,its time to implement this in python.See my other project in R.


```python

```
