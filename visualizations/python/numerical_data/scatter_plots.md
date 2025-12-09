# Scatter Plots

## Plotly Scatter Plot
```aiignore
# Compare Consistency vs Average Popularity
fig = px.scatter(
    artist_stats,
    x='mean',
    y='std',
    hover_data=['artist_name'],
    title='Artist Popularity: Consistency vs Average Popularity',
    labels={
        'mean': 'Average Popularity',
        'std': 'Consistency (Std Dev)'
    }
)
fig.show()
```

![Plotly Scatter Plot](images/plotly_scatter_plot.png)
