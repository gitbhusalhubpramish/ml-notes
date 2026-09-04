# Random Forest

This is a meachine learning algorithm which works by running multiple decision tree with same test data - collect there predictions, count the majority for classificaton or find the mean for regression and return that. This is a collection of tree.

## Make decision Tree

Decision trees are the building blocks of random forest. Therefore we should make a decision tree algorithm either classification or regression. But it has some changes. 

```py
def best_split(x,y,max_feature):
	n_features = x.shape[1]
	features = np.random.choice(n_features, size=max_features,replace=False)
	best = None
	bestscr = float("inf")
	for feature in features:

		#rest code
```

Here, we don't select all feature but select random feature and train tree according to that.

## Bootstrap

Here, random set to data are selected to train a tree.

```py
import numpy as np

def bootstrap(x,y):
	n = len(x)
	indices = np.random.choice(n,size=n,replace=True)
	return x[indices], y[indices]
```

**Where:**

- `np.random.choice(n,size=n,replace=True)` chooses the indices for data randomly `replace=True` may select 1 element multiple time.

## Make forest

Now trees are trained independently by bootstrap sample and the decision tree algorithm we made earlier.

```py
def build_forest(x,y, n_tree=20, max_depth=4):
	forest = []

	for _ in range(n_tree):
		xb,yb = bootstrap(x,y)
		tree = build_tree(xb,yb,depth=0,max_depth,max_depth)
		forest.append(tree)
	return forest
```

**Here:**

- We randomly choose the data for each tree randomly using bootstrap.
- Each tree is trained using the bootstrap data we choosed earlier.
- Multiple tree make a forest


