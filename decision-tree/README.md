# Decision tree

Decision tree is a meachine learning algorithm which works by asking question and creating new branch after each question.

The algorithm works by asking question and spliting the data into two new group.

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

Classification tree is a kind of decision tree which classifies the data. It is used to split data into classes.

For Example, we have:

```y = [1,2,2,1,1,3,1,2,3]```

After training the model the model will give us one of the value among 1,2 and 3 according to the data we feed; it won't return **mean**.

### How it works(trainning)

- **Check every possible split:** Here the algorithm tries to split data in every possible way and possible value of feature.

- **Calculate gini impurity:** The splited data is checked whether how pure is it - how distributed the catogary and classes are. The gini is calculated by this formula.

$$
Gini = 1 - \sum p^2
$$

- **Get the best split:** After checking every possible split and gini impurity the split with least impurity is selected and create 2 new branch where it might classify or again repete the decision making.

---

### In python

```
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier

xtrain, xtest, ytrain, ytest = train_test_split(x,y, test_size = 0.2, random_state=42, stratify=y)

model = DecisionTreeClassifier(max_depth=5, random_state = 42)
model.fit(xtrain, ytrain)

ypred = model.predict(xtest)
```

**Where:**

- `DecisionTreeClassifier` is the algorithm used to train decision tree classifier model.


