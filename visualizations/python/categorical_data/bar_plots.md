# Bar Plots
  
### Seaborn Horizontal Bar Graph
  
```aiignore
sns.barplot(
    data=df,
    y='Category_Name',
    x='Numerical_Column',
    palette='Set1'
)
```

![Seaborn Horizontal Bar Graph](images/seaborn_horizontal_bar_graph.png)
  
### Matplotlib Vertical Bar Graph
  
```aiignore
plt.bar(
    'category',
    'numerical_col'
)
plt.xlabel('Category')
plt.ylabel('Frequency')
plt.title('Title')
plt.xticks(rotation=45)
plt.show()
```
![MatPlotLib Vertical Bar Graph](images/matplotlib_vertical_bar_graph.png)


## Plotly Vertical Bar Graph

```aiignore
fig = px.bar(
    ldr_df.groupby(
        'album_name',
        as_index=False
    )['track_popularity'].mean(),
    x='album_name',
    y='track_popularity',
    color='album_name',
    title='Average Track Popularity by Album',
    labels={
        'track_popularity': 'Average Popularity',
        'album_name': 'Album'
    },
    text='track_popularity'
)

# Format text labels to 0 decimals
fig.update_traces(texttemplate='%{y:0f}')

fig.show()
```

![Plotly Vertical Bar Graph](images/plot_vertical_bar_graph.png)

