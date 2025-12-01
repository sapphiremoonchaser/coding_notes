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


