### Date and Time Manipulation

`DATE_TRUNC('month', order_date)`  
`DATE_ADD(order_date, INTERVAL 7 DAY)`  
`DATEDIFF(day, start_date, end_date)`


### Moving windows with time-based windows
```aiignore
SUM(amount) OVER (
    ORDER BY date 
    RANGE BETWEEN INTERVAL '7 days' PRECEDING AND CURRENT ROW
)
```

