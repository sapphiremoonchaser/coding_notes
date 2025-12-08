# Correlation Matrix
  
```aiignore
# Select numerical columns only
numerical_columns = df.select_dtypes(
    include=[np.number]
)

# Create the Correlation Matrix
corr_matrix = numerical_columns.corr()

# Plot correlation matrix as a heat map
plt.figure(
    figsize=(12, 8)
)

sns.heatmap(
    corr_matrix,
    annot=True, # Shows correlation values in cells
    fmt=".2f",
    cmap="coolwarm",
    square=True,
    cbar_kws={'shrink': 0.8} # Makes color bar smaller
)
plt.title("Correlation Matrix of ... ", fontsize=14)
plt.tight_layout()
plt.show()
```

![Correlation Matrix](images/correlation_matrix.png)