# Label Encoding
  
### Sort into Cat or Num Columsn

by count of unique values
  
```aiignore
columns = list(df.columns)
categorical_columns = []
numerical_columns = []

for i in columns:
    if len(df[i].unique()) > 24:
        numerical_columns.append(i)
        
    else:
        categorical_columns.append(i)
```
  
by dtype

```aiignore
categorical_columns = []
numerical_columns = []

for column in df.columns:
    if df[column].dtype == 'object':
        categorical_columns.appen()
        
    else:
        numerical_columns.append()
```

### Label Encoding
  
`from sklearn.preprocessing import LabelEncoder`

one column

```aiignore
le = LabelEncoder()
y_encoded = le.fit_transform(y)
```

```aiignore
label_encoder = LabelEncoder()

for column in df.columns:
  if df[column].dtype == 'object': # Categorical Column
    df[column] = labelencoder.fit_transform(df[column])
```

