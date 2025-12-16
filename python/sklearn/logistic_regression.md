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

### Predictions

`from sklearn.metrics import classification report`

```aiignore
y_pred = model.predict(X_test)

print(
    classification_report(
        y_test,
        y_pred,
        target_names=le.classes_
    )
)
```