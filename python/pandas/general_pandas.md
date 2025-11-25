## Viewing and Inspecting Data

```aiignore
df.head()         # first 5 rows
df.tail()         # last 5 rows
df.info()         # column types, missing values
df.describe()     # summary stats
df.shape          # (rows, columns)
df.columns        # column names
df.index          # row index
  
```

## Value Counts and Unique

```aiignore
df["col"].value_counts()
df["col"].nunique()
df["col"].unique()
```

## Missing Data
  
### Count missing data per column

`df.isna().sum()`


### Drop rows with ANY missing data
  
`df.dropna()`

### Drop rows where specific columns have missing data

```aiignore
df.dropna(
    subset=["col"]
)
```

## Sorting

```aiignore
df.sort_values("age")  
df.sort_values("age", ascending=False)
df.sort_values(["age", "name"])
```

## Group By

`df.groupby("category")["sales"].sum()`

### multiple aggregations 

```aiignore
df.groupby("team").agg({
    "score": "mean",
    "age": "max"
})
```

## Merging and Joining

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

## Pivot Tables

```aiignore
pd.pivot_table(
    df,
    values="sales",
    index="month",
    columns="region",
    aggfunc="sum"
)
```