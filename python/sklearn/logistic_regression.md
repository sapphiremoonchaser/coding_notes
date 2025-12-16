# Logistic Regression

`from sklearn.linear_model import LogisticRegression`

### Training

```aiignore
# Train a simple logistic regression model
model = LogisticRegression(
    max_iter=1000
)

model.fit(
    X_train,
    y_train
)
```