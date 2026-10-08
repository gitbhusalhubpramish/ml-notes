# K-means

K-means is a unsupervised clustering Meaching Learning Algorithm. It Cluster the given data through Centroid - It cluster by measuring distance. A data is clusterized through it's nearest centroid.

## Clustering

The group of point with the same centroid are known as Clusters. A cluster is calculated by:

$$
cluster_i = \arg \min_k d(x_i,c_k)
$$

**Where:**

$$
d(x,c) = \sqrt{sum_{i} (x_j - c_j)^2}
$$
