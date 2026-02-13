# Linear Fit for Comparison

```aiignore
# Compute expected efficiency
# Using linear fit
# Use log transform for stability
df_overperformers = df_overperformers.assign(
    log_total_medals=np.log1p(df_overperformers['total_medals'])
)

coef = np.polyfit(
    df_overperformers['log_total_medals'],
    df_overperformers['efficiency_per_capita'],
    1
)

df_overperformers['expected_efficiency'] = (
    coef[0] * df_overperformers['log_total_medals'] + coef[1]
)

df_overperformers
```