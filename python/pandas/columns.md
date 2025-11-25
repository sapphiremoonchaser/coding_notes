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

## Apply, Map, Applymap

### Apply on a column

```aiignore
df['double'] = df['num'].apply(
    lambda x: x*2
)
```

### Map on a Column

```aiignore
df['grade'] = df['score'].map({
    90: "A",
    80: "B"
})
```

### Apply on an entire DataFrame

```aiignore
df.applymap(
    lambda x: x if isinstance(x, str) else round(x, 2)
)
```

