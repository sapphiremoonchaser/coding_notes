# Histograms

## Make a histogram for all numerical columns

```aiignore
ldr_df.hist(
    figsize=(14,10),
    bins=30,
)
plt.suptitle("Numerical Columns Distributions")
plt.show()
```

![Multiple Histograms](images/histograms_multiple.png)


# Box Plots

## Seaborn Box Plots

```aiignore
top5 = consistent_artists['artist_name'].head(5)

sns.boxplot(
    data=df_small[
        df_small['artist_name'].isin(top5)
    ],
    x='artist_name',
    y='track_popularity'
)

plt.title('Popularity Distribution of Top 5 Most Consistent Artists')
plt.xticks(rotation=45)
plt.show()
```

![Seaborn Box Plot](images/seaborn_box_plot.png)


# Combos

## Plotly Hist/Box Plot for a specific Metric

```aiignore
# Distribution Comparison of artist_type and avg_popularity
sns.boxplot(
    data=artist_features,
    x='artist_type',
    y='avg_popularity'
)

plt.title('Average Popularity by Artist Type')
plt.show()
```

![Plotly Hist and Box Plot](images/plotly_hist_box_plot.png)
