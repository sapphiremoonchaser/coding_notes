# Train/Test Split

`from sklearn.model_selection import train_test_split`

```aiignore
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y_encoded,
    test_size=0.3,
    random_state=42,
    stratify=y_encoded
)
```