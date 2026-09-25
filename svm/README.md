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

## Linear SVM

This is a simple svm model which has a simple linear dicision line and where model predict it as a class if it's y is above the decision line else it predict as another class.

It's decision line looks something like this:

$$
y = wx+b
$$

**Where:**

- $w$ is the weight.
- $b$ is the bias.
- $x$ is the input data

### Loss

Here we use the Huge loss formula

$$
L = max(0, 1-y_i \hat{y_i}
$$

**Here:**

- $y_i$ is the true y.
- $\hat{y_i}$ is the predicted y.

### Greadients and it's decent

The greadient looks like this

$$
\frac{\partial L}{\partial w} = -y_i x_i
$$

The greadient decient is same as every other algorithm:

$$
w = w - \frac{\partial L}{\partial w}
$$
