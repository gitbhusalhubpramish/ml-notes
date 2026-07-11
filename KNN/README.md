# KNN
KNN stans **K<sup>th</sup> Nearest Neighbour**. It is also called Lazy algorithm because it doesn't use gredient decent and maths while training.

It stores training data, gets new point, calculate the **distance** between new point and training data, sort them and gives output according to **majority votes**.

**For Example:**

  If a new point is given to model, it calculates distance between all training point it has stored and sort the distance.

  It picks the first k distance from sorted distance and counts the mode and give the mode as output.

