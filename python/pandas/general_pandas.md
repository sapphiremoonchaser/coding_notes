## Viewing and Inspecting Data

```aiignore
df.head()         # first 5 rows
df.tail()         # last 5 rows
df.info()         # column types, missing values (count per column)
df.describe()     # summary stats (count, mean, std, quantiles)
df.shape          # (rows, columns)
df.columns        # column names
df.index          # row index
```

## Custom Summary Stat DataFrame 

```aiignore
summary = pd.DataFrame({
    'stat': ['min', 'mean', 'median', 'max'],
    'avg_time_to_throw': [
        passer_df_pts['avg_time_to_throw'].min(),
        passer_df_pts['avg_time_to_throw'].mean(),
        passer_df_pts['avg_time_to_throw'].median(),
        passer_df_pts['avg_time_to_throw'].max()
    ]
})
```

## Value Counts and Unique

```aiignore
df["col"].value_counts()
df["col"].nunique() # Unique Count by column
df["col"].unique()
```

## Rename Specific Column
df = df.rename(
    columns = {
        "old_name": "name_name"
    }
)

## Rename specif values
```aiignore
ldr_df.loc[
    ldr_df['column_to_replace_in'].str.contains(
        'string_to_be_replaced',
        case=False,
        na=False
    ),
    'column_to_look_through'
] = 'string_to_replace'
```

## Rename Specific values with list or regex
```aiignore
# Rename Born To Die versions to 'Born To Die'
btd_version_patterns = [
    'Born To Die',
    'Summertime Sadness'
]

ldr_df.loc[
    ldr_df['album_name'].str.contains(
        '|'.join(btd_version_patterns),
        case=False,
        na=False
    ),
    'album_name'
] = 'Born To Die'
```

## Missing Data
  
#### Count missing data per column

`df.isna().sum()`


Drop rows with ANY missing data
  
`df.dropna()`

#### Drop rows where specific columns have missing data

```aiignore
df.dropna(
    subset=["col"]
)
```

## Check for Duplicated Data
  
`df.duplicated().sum()`

## Sorting

```aiignore
df.sort_values("age")  
df.sort_values("age", ascending=False)
df.sort_values(["age", "name"])
```

#### Sorting a list and specifying ascending
```aiignore

df_grouped = df_grouped.sort_values([
    'year',
    'track_popularity'
],
ascending=[
    True,
    False
])
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




