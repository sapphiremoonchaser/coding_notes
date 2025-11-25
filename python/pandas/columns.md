### List columns

`df.columns`

### Adding and Updating Columns
```aiignore
df["new_col"] = df["age"] * 2
df["is_adult"] = df["age"].apply(lambda x: x >= 18)
df["constant"] = 1
```

#### Using .assign
```aiignore
df = df.assign(
    score=df.age * 1.5
)
```

### Renaming Columns
  
```aiignore
df = df.rename(
    columns={
        "old": "new"
    }
)
```

### Rename to lowercase, snake_case, etc.
  
```aiignore
df.columns = df.columns.str.lower()
df.columns = df.columns.str.replace(" ", "_")
```

