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
fig = px.line(
    top_artists_last_10,
    x='year',
    y='track_popularity',
    title='Average Track Popularity by Year',
    markers=True,
    labels={
        'track_popularity': 'Average Popularity',
        'year': 'Year'
    }
)

fig.show()
```

![Plotly Line Chart](images/plotly_line_chart.png)