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

## Classification tree

Classification tree is a kind of decision tree which classifies the data. It is used to split data into classes.

For Example, we have:

```y = [1,2,2,1,1,3,1,2,3]```

After training the model the model will give us one of the value among 1,2 and 3 according to the data we feed; it won't return **mean**.


