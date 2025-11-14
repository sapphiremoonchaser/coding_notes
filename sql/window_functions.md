### Ranking & Row Navigation
  
`ROW_NUMBER() OVER (PARTITION BY category ORDER BY price DESC)`  
`RANK() OVER (PARTITION BY dept ORDER BY salary DESC)`  # same rank to tied values, skips values (1,2,2,4)
`DENSE_RANK() OVER (...)`  # same rank to tied values, does not skip values (1,2,2,3)
`NTILE(4) OVER (ORDER BY score DESC)`


### Led and Lag
`LAG(sales, 1) OVER (ORDER BY date)`
`LEAD(sales, 1) OVER (ORDER BY date)`


### Running Totals
```aiignore
SUM(revenue) OVER (
    ORDER BY date 
    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
    )
```

### Moving Averages
```aiignore
AVG(price) OVER (
    ORDER BY date 
    ROWS 3 PRECEDING
    )
```


