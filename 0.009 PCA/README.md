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

After this the mean of the data becomes 0. This prevents parameter be unnecessary large - very unsensetive at some point while very sensetive at some

**Standardization**

This refers to make the stander deviation of the data 1 after mean centirng. We standardizate by:

$$
X' = \frac{X-\bar{X}}{\sigma}
$$

This ensures constant sensetivity of parameter upto a fix point

## Covariance matirces

This is the matrix of how a component is related to other components in the dataset. We calculate covariance by:

$$
Cov(x,y) = \frac{1}{n} \sum_{i} (x_i - \mu_i)(y_i - \mu_y)
$$

To get a covariance matrix we do:

$$
C = \begin{bmatrix} Var(X) && Cov(X,Y) && Cov(X,Z) \\
Cov(X,Y) && Var(Y) && Cov(Y,Z) \\
Cov(X,Z) && Cov(Y,Z) && Var(Z)
\end{bmatrix}
$$
