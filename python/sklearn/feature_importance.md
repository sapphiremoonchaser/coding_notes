# Feature Importance
  
For Correlation Matrix code look under the visualizations directory. 

## Linear Regression Feature Importance

`from sklearn.linear_model import LinearRegression`

```aiignore
# Define the model
model = LinearRegression()

# Fit the model
model.fit(X, y)

# Get importance (coeff. of the features)
importance = model.coef_

# Plot feature importance
plt.bar(
    X.columns,
    importance
)
plt.xlabel('Feature')
plt.ylabel('Importance Score')
plt.title('Feature Importance from Linear Regression')
plt.xticks(rotation=45)
plt.show()

# Summarize feature importance
# Feature: Name, Score: -1.0707"
for feature, score in zip(X.columns, importance):
    print(f'Feature: {feature}, Score: {score}')
```

## Decision Tree Feature Importance

`from sklearn.tree import DecisionTreeRegressor`

```aiignore
# Define the model
model = DecisionTreeRegressor()

# Fit the model
model.fit(X, y)

# Get importance of features
importance = model.feature_importances_

# Plot feature importance
plt.bar(X.columns, importance)
plt.xlabel('Feature')
plt.ylabel('Importance Score')
plt.title('Feature Importance from Decision Tree Regressor')
plt.xticks(rotation=45)  # Rotate the x labels if they are too long
plt.show()

# Summarize feature importance
for feature, score in zip(X.columns, importance):
    print(f'Feature: {feature}, Score: {score:.5f}')
```

## XGBoost Feature Importance

`from xgboost import XGBRegressor`

```aiignore
# Define the model
model = XGBRegressor()

# Fit the model
model.fit(X,y)

# Get importance (feature importances of the features)
importance = model.feature_importances_

# Plot feature importance
plt.bar(X.columns, importance)
plt.xlabel('Feature')
plt.ylabel('Importance Score')
plt.title('Feature Importance from XGBoost Regressor')
plt.xticks(rotation=45)  # Rotate the x labels if they are too long
plt.show()

# Summarize feature importance
for feature, score in zip(X.columns, importance):
    print(f'Feature: {feature}, Score: {score:.5f}')
```

## Permutation Importance with KNN

`from sklearn.neighbors import KNeighborsRegressor`
`from sklearn.inspection import permutation_importance`

```aiignore
# Define the model
model = KNeighborsRegressor()

# Fit the model
model.fit(X,y)

# Calculate Permutation Feature Importance
result = permutation_importance(
    model,
    X,
    y,
    n_repeats=30,
    random_state=42,
    n_jobs=1
)

# Extract feature importance
importance = result.importances_mean

# Plot feature importance
plt.bar(X.columns, importance)
plt.xlabel('Feature')
plt.ylabel('Importance Score')
plt.title('Feature Importance using Permutation Importance with KNN Regressor')
plt.xticks(rotation=45)  # Rotate the x labels if they are too long
plt.show()

# Summarize feature importance
for feature, score in zip(X.columns, importance):
    print(f'Feature: {feature}, Score: {score:.5f}')
```