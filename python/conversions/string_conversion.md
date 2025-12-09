# str -> List

```aiignore
# Convert 'artist_genres' from string formatted as a list to a List
df_small['artist_genres'] = df_small['artist_genres'].apply(
    lambda x: ast.literal_eval(x) if isinstance(x, str) else x
)
```

