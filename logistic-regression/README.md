# Logistic Regression
Logistic Regression is a ML algorithm which is used for data output like true or false. It wraps Linear output in a function called sigmodi($\sigma$).

It stands:

$$
\hat{y} = \sigma (z)
$$

where:

$$
\sigma (z) = \frac{1}{1+e^-z}
$$

and 

$$
z = mx+b
$$

---

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

where:

- `LogisticRegression` is the model class in sklearn so we can train and test model

---

## Error/Accuracy of a model

**Error** of a Logistic Regression model can be calculated by the given formula

$$
L = - \frac{1}{n} \sum y log(\hat{y})+(1-y) log(1-\hat{y})
$$

where:
 
- $y$ is the expeted output
- $\hat{y}$ is the model output

*this is also called binary cross entropy loss*

**In python**

```py
from sklearn.metrics import log_loss
loss = log_loss(prediction, y)
```

where:

- `prediction` is the model output
- `y` is the expected output

---

**Accuracy** of a model can be calculated by

$$
Accuracy = \frac{number of correct prediction}{total number of data}
$$

**In python**

```py
from sklearn.metrics import accuracy_score
accuracy_score(prediction, y)
```

where:

- `prediction` is the model output
- `y` is the expected output

---

## Gradient

**w.r.t. w**

$$
\frac{\partial L}{\partial w} = \frac{1}{n} \sum (\hat{y} - y) X^T
$$

**w.r.t. b**

$$
\frac{\partial L}{\partial b} = \frac{1}{n} \sum (\hat{y} - y) 
$$

where:

- $y$ is the expected output
- $\hat{y}$ is the model ouput
- $X$ is the input

---

## Gradient dicent

**for weight**

$$
w = w - \alpha \frac{\partial L}{\partial w}
$$

where:

- $\alpha$ is the learning rate
- $\frac{\partial L}{\partial w}$ is the gradient for weight

**for bios**

$$
b = b - \alpha \frac{\partial L}{\partial b}
$$


where:

- $\alpha$ is the learning rate
- $\frac{\partial L}{\partial b}$ is the gradient for bios
