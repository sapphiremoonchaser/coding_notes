# Merging and Joining

### Inner Join
  
```aiignore
pd.merge(
    df1,
    df2,
    on="id"
)
```

### Left, Right, Outer Join

```aiignore
pd.merge(
    df1,
    df2,
    on="id",
    how="left" # "right", "outer", "inner"
)
```

### Stack Rows

```aiignore
pd.concat(
    [df1, df2],
    axis=0
)
```

### Stack Columns

```aiignore
pd.concat(
    [df1, df2],
    axis=1
)
```

### Pivot Tables

```aiignore
pd.pivot_table(
    df,
    values="sales",
    index="month",
    columns="region",
    aggfunc="sum"
)
```