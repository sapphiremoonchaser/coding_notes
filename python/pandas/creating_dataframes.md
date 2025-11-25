## From One Dict
  
```aiignore
df = pd.DataFrame({
    "name": ["A", "B", "C"],
    "age": [23, 24, 25]
})
```

## From List of Dicts
  
```aiignore
df = pd.DataFrame([
    {"name": "A", "age": 23},
    {"name": "B", "age": 34}
])
```

## From CSV

`df = pd.read_csv("file.csv")`