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

When we have a lot of feature multipling all the probability(values less than 0) returns very small number which is concidered as 0 by the computer. For Example:

If we have 100 features and each class has probability of avrage of 0.4,

So, the $P(A|B)$ becomes $1.6 * 10^40$ which is concidered as $0$ by the computer.

**The solution:**

We take the log score

Since, 

$$
\log(ab) = \log(a) + \log(b)
$$

And,

If $a<b$,

Then, 

$$
\log(a)<\log(b)
$$


Therefore we calculate score by:

$$
\boxed{\log(P(A|B)) = \log(A) \sum_i \log(P(B|A))}
$$
 
### Final prediction

Rather than relaying on only one class A we also calculate pobability for class $\bar{A}$ too.

We first calculate,

$$
P(A|b)
$$

And,

$$
P(\bar{A}|B)
$$

Then data is concidered as class A if,

$$
P(A|B)>P(\bar{A}|B)
$$

## Categorical Naive Bayes

This is a simole and classic naive bayes algorithm which uses probability of being a part of class by feature class. Here Its features are catogral too - usually words like `["Doctor", "Engineere"]` for predicting whether a person passed from a engineering collage.

The formula for $P(B|A)$ is the only thing which makes it different. And it seems like this

$$
P(B|A) = \frac{n(B)}{n(A)}
$$

**Where:**

- $n(A)$ is the number of Class A in the data.
- $n(B)$ is the number of Class B in the feature Class.

## Gussian Naive Bayes

This is used for numeric value where categorial can only predict if feature class is in training data while Gussian draws a Gussian graph in the form of $e^{-x}$ whose area is 1.

The formula for $P(B|A)$ seems like this:

$$
P(B|A) = \frac{1}{\sqrt{2 \pi} \sigma_A} e^{- \frac{(B-\mu_A)^2}{2 \sigma_y^2}}
$$

**Where:**

- $B$ is the value of a feature in tesing data.
- $\sigma_A$ is the stander deviation of values of feature B with class A.
- $\mu_A$ is the mean of values of feature B with class A.

