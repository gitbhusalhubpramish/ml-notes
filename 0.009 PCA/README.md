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

## Eigenvectors and Eigenvalues

Both are very useful components of PCA. Eigenvectors transforms the data or the direction of new axis(principal components) and Eigenvalues are the variance of the data spread in each principal components.

They relate by:

$$
Cv= \lambda v
$$

**Eigenvectors**

This is the direction of new axis(principal component). It transforms the data in new dimention. There are $n$ dimention(element) in a Eigenvector where $n$ is the number of feature. To find Eigenvector we do:

It is calculated by:

$$
(C - \lambda I) v = 0
$$

**Where:**

- $\lambda$ is the Eigenvalues
- $v$ is the Eigenvector
- $I$ is the identity matrix

**Eigenvalues**

This is the spreadness of data in corresponding axis. It is used to arrange the Eigenvectors to keep higest variance or eigenvectors holding most information in a PCA. To calculate this we do:

$$
\det(C - \lambda I) = 0
$$

Then we sort it in a matrix $W$ so that.

$$
\lambda_1 \geq \lambda_2 \geq \lambda_3 \geq ... \geq lambda_n
$$

and $W$ looks like this:

$$
W = \begin{bmatrix} v_1 && v_2 && v_3 && ... && v_n \end{bmatrix}
$$

### Calculating in numpy

We don't have a fix formula to calculate this so we use a function in numpy to calculate eigenvectors and eigenvalues in numpy. 

```py
import numpy as np

lam, v = np.linalg.eigh(c)
```

**Where:**

- `lam` is the Eigenvalues.
- `v` is the Eigenvectors.
- It is not sorted with coresponding variance so we have to sort in decending order according to corresponding variance.

