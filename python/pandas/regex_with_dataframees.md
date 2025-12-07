# Strings  that are formatted like Lists

```aiignore
# Create mask (True/False matching)
mask = artist_genres_df['artist_genres'].str.contains(
    r"\beast coast hip hop\b",
    regex=True
)

# Look for artists where mask it True
pop_soul_artists = artist_genres_df.loc[
    mask,
    'artist_name'
].tolist()
```