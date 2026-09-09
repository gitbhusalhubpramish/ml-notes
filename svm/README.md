# SVM

SVM(support vector machine) is a meachine learning model where the model draw a decision line from where it classifies data. It is supervised regression-bashed classification meachine learing algorithm. Decision line looks like this:

$$
w^T x + b = 0
$$

**Where:**

- $w^T$ is the weight of model
- $x$ is the input point
- $b$ is the bias

*This is just a simple SVM model. Real one is even more scary!*

## Prediction

The formula given above is just decison line. When any value of x returns $\leq 0$ it is classified as different class and if it returns $>0$ it is different class

**Note:** *SVM classifies data into only 2 classes.*

$$
z = w^T x + b 
$$

**Here:**

If:

$$
z \leq 0
$$

**Then:**

$$
\hat{y} = -1
$$

Else:

$$
\hat{y} = 1
$$
