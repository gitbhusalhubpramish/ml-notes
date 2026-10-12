# Principle Component Analysis(PCA)

This is a simple classic unsupervised Meachine Learning algorithm wihch simplifies complex data to simple data while keeping important information. It makes it's own feature(axis) so that it include information of most of the axis and makes anylasis easier.

There are n unmber of PCA in any PCA where n is the number of feature.

## Principle axis

This is the machine-made axis which has the higest number of variance in data so that it include maximum information in data. There are n number of Principle axis where n is the number of feature.

## Mean-centering and Standardization

Both are before training processes where we optmize data before training or feeding to model. 

**Mean-centering**

This simpilly refers to make the mean of data 0. We do centring by:

$$
X' = X-\bar{X}
$$
