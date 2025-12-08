# Make a histogram for all numerical columns

```aiignore
ldr_df.hist(
    figsize=(14,10),
    bins=30,
)
plt.suptitle("Numerical Columns Distributions")
plt.show()
```

![Multiple Histograms](images/histograms_multiple.png)


# Plotly Hist/Box Plot for a specific Metric

```aiignore
fig = px.histogram(
    ldr_df,
    x='track_popularity',
    color='album_name',
    barmode='overlay',
    nbins=30,
    title='Track Popularity by Album',
    marginal='box'
)
fig.show()
```

![Plotly Hist and Box Plot](images/plotly_hist_box_plot.png)
