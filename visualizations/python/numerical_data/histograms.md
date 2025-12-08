# Make a histogram for all numerical columns
df.hist(figsize=(14,10),bins=30)
plt.suptitle('Numerical Columns Distributions')
plt.show()