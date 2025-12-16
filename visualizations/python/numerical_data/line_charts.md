# Line Charts

## Matplotlib Line chart

```aiignore
# line chart using matplotlib
plt.figure(figsize = (10,5))

plt.plot(
    top_artists_last_10['year'],
    top_artists_last_10['track_popularity'],
    marker='o',
    linestyle='-'
)

plt.title('Average Track Popularity by Year')
plt.xlabel('Year')
plt.ylabel('Track Popularity')
plt.grid(True)
plt.xticks(top_artists_last_10['year']) # show each year
plt.show()
```

![Matplotlib Line Chart](images/matplotlib_line_chart.png)


## Seaborn Line Chart

```aiignore
# Line chart using seaborn
plt.figure(figsize = (10,5))

sns.lineplot(
    data=top_artists_last_10,
    x='year',
    y='track_popularity',
    marker='o'
)

plt.title('Average Track Popularity by Year')
plt.xlabel('Year')
plt.ylabel('Track Popularity')
plt.grid(True)
plt.show()
```

![Seaborn Line Chart](images/seaborn_line_chart.png)


## Plotly Line Chart

```aiignore
# Get the top artists from previously created df
top_artists = top_consistent_artists['artist_name']

# Filter to only the top artists
plot_data = avg_track_pop_by_artist_decade[
    avg_track_pop_by_artist_decade['artist_name'].isin(top_artists)
]

fig = px.line(
    plot_data,
    x='decade',
    y='track_popularity',
    color='artist_name',
    markers=True,
    title='Popularity Trajectories of Long-Lasting Artists',
    labels={
        'artist_name': 'Artist',
        'track_popularity': 'Popularity',
        'decade': 'Decade'
    }
)
fig.show()
```

![Plotly Line Chart](images/plotly_line_chart.png)