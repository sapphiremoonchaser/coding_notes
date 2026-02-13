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


## MatPlotLib with trendline
```aiignore
# Plotting overperformers with trend line (via numpy)
x = df_efficiecy["total_medals"]
y = df_efficiecy["efficiency_per_capita"]
coef = np.polyfit(np.log1p(x), y, 1)

# Generate a smooth x-range
x_line = np.linspace(x.min(), x.max(), 200)

# Compute the trend line
y_line = coef[0] * np.log1p(x_line) + coef[1]

# plot
plt.figure()

# Scatter plot
plt.scatter(
    x,
    y
)

# One smooth trend line
plt.plot(
    x_line,
    y_line
)

plt.xlabel("Total Medals")
plt.ylabel("Efficiency")
plt.title("Identifying Olympic Medal Overperformers")
plt.show()
```

