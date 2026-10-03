# Naive Bayes

Naive Bayes is a Supervised Meachine Learning algorithm which uses Probality to predict any output. This is a Probabilistic classifiers model.

It seems something like this:

$$
P(A|B) = \frac{P(A)P(B|A)}{P(B)}
$$

## Prediction

### Direct probability calculation

It simplly calculate the probability of being class A according to feature class B.

$$
P(A|B) = \frac{P(A) P(B|A)}{P(B)}
$$

**Where:**

- $P(A|B)$ is the prob of being class A according to feature Class B.
- $P(A)$ is the prob of being class A from total number of data.
- $P(B|A)$ is the prob of feature B's each class being in class A.
- $P(B)$ is the prob of class B to be in a feature.

**For multiple Classes:**

We simply multiply the probability of being in class A according to all feature Class B then multiiply it by probability of being in class A through total data.

$$
P(A|B) \propto P(A) \prod_{i} P(B_i|A)
$$


### Log score calculation

When we have a 

## Categorical Naive Bayes

This is a simole and classic naive bayes algorithm which uses probability of bei
ng a part of class by feature class. Here Its features are catogral too - usuall
y words like `["Doctor", "Engineere"]` for predicting whether a person passed fr
om a engineering collage.

