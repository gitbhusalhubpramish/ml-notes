# Logistic Regression
Logistic Regression is a ML algorithm which is used for data output like true or false. It wraps Linear output in a function called sigmodi($\sigma$).

It stands:

$$
\hat{y} = \sigma (z)
$$

where:

$$
\sigma (z) = \frac{1}{1+e^z}
$$

and 

$$
z = mx+b
$$

## In python

```py
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

df = pd.read_csv("data.csv")

x = df[["x"]]
y = df["y"]

xtrain,xtest,ytrain,ytest = train_test_split(x,y,test_size = 0.2, random_state = 42)

model = LogisticRegression()
model.fit(xtrain,ytrain)

pred = model.predict(xtest)
```
