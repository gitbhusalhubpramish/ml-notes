# Decision tree

Decision tree is a meachine learning algorithm which works by **asking question** and creating new **branch** after each question.

The algorithm works by asking question and **spliting** the data into two new group.

## How it works?

Before learning how to train a model in decision tree algorithm we must learn how it works or how to use it. 

```
		x>thrshold?
			/\
		no     /  \ yes
		      /    \
		     /       \
		leaf 1 split| leaf 2 split
```

Here we have:

- **Threshold:** It is the value which split data into two part.
- **Branch:** New branch are again split from a threshold or classified.
- **Depth:** It refers to how many decision does a tree make.

---

## Classification tree

Classification tree is a kind of decision tree which **classifies** the data. It is used to split data into **classes**.

**For Example**, we have:

```y = [1,2,2,1,1,3,1,2,3]```

After training the model the model will give us one of the value among 1,2 and 3 according to the data we feed; it won't return **mean**.

### Spliting

Here the data is splited into two branches left and right from a value of a feature called treshold. The spliting take place after every node untill it reach a leaf where it classifies the classes.

### Gini impurity

This is a important step of a decision tree while trainning. It checks how pure a split or classification is. To calculate gini on classification leaf we use this formula.

$$
Gini = 1- \sum (\frac{n_{class}}{n_{total}})^2
$$

**Where:**

- $n_{class}$ is the number of element of that class.
- $n_{total}$ is the sum of number of all element.

### Best split

A treshold or split is concidered as best treshold or split when it split data with least impurity. To calculate split score we use this formula.

$$
split score = \frac{n_{left}}{n_{total}} Gini(left) + \frac{n_{right}}{n_{total}} Gini(right)
$$

**Where:**

- $n_{left}$ and $n_{right}$ is the number of element in left and right node
- $n_{total}$ is the sum of $n_{left}$ and $n_{right}$
- $Gini(left)$ and $Gini(right)$ is the impurity of left and right node

---

### In python

```py
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier

xtrain, xtest, ytrain, ytest = train_test_split(x,y, test_size = 0.2, random_state=42, stratify=y)

model = DecisionTreeClassifier(max_depth=5, random_state = 42)
model.fit(xtrain, ytrain)

ypred = model.predict(xtest)
```

**Where:**

- `DecisionTreeClassifier` is the algorithm used to train decision tree **classifier model**.

---

## Regression tree

Regression tree is another decision tree algorithm which classifies data through **mean** and uses number rather than name. 

For example, we have:

`y = [1,2,1,2,3,1,2,1,3]`

The algorithm will split the data and return the **mean** as output; it won't return classes.

### How it works

- **Check every possible split:** Here the algorithm tries to split data in every possible way and possible value of feature.

- **Calculate MSE:** Unlike classification tree it doesn't classifies the data into classes rather it return the **mean** and the error is calculated through MSE.

$$
MSE = \frac{1}{n} \sum (y - \hat{y})^2
$$

- **Find best split:** *same as classification.*

---

### In python

```py
from sklearn.tree import DecisionTreeRegression
from sklearn.model_selection import train_test_split

xtrain, xtest, ytrain, ytest = train_test_split(x,y, test_size=0.2, random_state=42, stratify-y)

model = DecisionTreeRegression(max_depth=5, random_state=42)
model.fit(xtrain, ytrain)

ypred = mode.predict(xtest)
```

**Where:**

- `DecisionTreeRregression` is the algorithm used to train **regression model**.
