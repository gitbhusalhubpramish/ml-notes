# KNN
KNN stans **K<sup>th</sup> Nearest Neighbour**. It is also called Lazy algorithm because it doesn't use gredient decent and maths while training.

It stores training data, gets new point, calculate the **distance** between new point and training data, sort them and gives output according to **majority votes**.

**For Example:**

  If a new point is given to model, it calculates distance between all training point it has stored and sort the distance.

  It picks the first k distance from sorted distance and counts the mode and give the mode as output.

**How to choose k**

Choosing k might play important role in model accuracy especially in noise

- Choosing **large** value(30,40,50):

  - Might ignore important local pattern

- Choosing **small** value(1,2,3):

  - Might be sensetive to noise

- **choosing right value**

$$
k \approx \sqrt{n}
$$

## In python(sklearn)

```py

```
