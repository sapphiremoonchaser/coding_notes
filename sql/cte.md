### Basic CTE
```aiignore
WITH sales_by_day AS (
    SELECT date, SUM(total) AS revenue
    FROM orders
    GROUP BY date
)

SELECT *
FROM sales_by_day
WHERE revenue > 1000;
```

### Recursive CTE
```aiignore
WITH RECURSIVE nums AS (
    SELECT 1 AS n
    UNION ALL
    SELECT n + 1 FROM nums WHERE n < 10
)
SELECT * FROM nums;
```