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

This is a simole and classic naive bayes algorithm which uses probability of bei
ng a part of class by feature class. Here Its features are catogral too - usuall
y words like `["Doctor", "Engineere"]` for predicting whether a person passed fr
om a engineering collage.

