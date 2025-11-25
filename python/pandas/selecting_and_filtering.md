### Selecting Columns
   
`df['col']`
`df['col1', 'col2']`

### Selecting rows
  
```aiignore
df.loc[3]                   # by index label
df.iloc[3]                  # by row number
df.loc[3, "col"]            # specific cell (label)
df.iloc[3, 2]               # specific cell (position)
```

### Conditional Filtering
```aiignore
df[df["age"] > 30]
df[(df["age"] > 20) & (df["age"] < 40)]
df[df["name"].isin(["A", "C"])]
df[df["name"].str.contains("a", case=False)]
```