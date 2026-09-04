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

