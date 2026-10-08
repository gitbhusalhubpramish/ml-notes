# K-means

K-means is a unsupervised clustering Meaching Learning Algorithm. It Cluster the given data through Centroid - It cluster by measuring distance. A data is clusterized through it's nearest centroid.

## Clustering

The group of point with the same centroid are known as Clusters. A cluster is calculated by:

$$
cluster_i = \arg \min_k d(x_i,c_k)
$$

**Where:**

$$
d(x,c) = \sqrt{\sum_{i} (x - c)^2}
$$

## Cost function

Since, it is a unsupervised algorithm so we don't have $y$ and $\hat{y}$ but we simpilly calculate the distance between centroid and datapoints.

$$
J = \sum_k \sum_{i \in C_k} ||x_i - c_k||^2
$$

**Where:**

- $C$ are the point belonging to the cluster.
- $c$ is the centroid of a cluster.

## Optmizing centroid

Same as other Supervised learning algorithm, We must optmize the paramater. Parameter for this algoritm is the centrod so we must optmize centroid to minimize the cost function. First we select random centroid and do this operation:

$$
c_j = \frac{1}{||C_j||} \sum_{i \in C_j} x_i
$$
