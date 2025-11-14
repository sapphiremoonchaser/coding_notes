| Feature                   | CTE (Common Table Expression) | Temporary Table            | Materialized View                   |
| ------------------------- | ----------------------------- | -------------------------- | ----------------------------------- |
| Persistence               | Only during the query         | During the session         | Persistent (stored)                 |
| Performance               | Not cached; recalculated      | Can improve performance    | Best performance for repeated reads |
| Modifiable?               | No                            | Yes (insert/update/delete) | No (must refresh)                   |
| Good for?                 | Readability & structure       | Complex multi-step work    | Fast repeated queries               |
| Self-reference?           | Only recursive CTEs           | No                         | No                                  |
| Expensive queries cached? | ❌ No                          | ❌ No                       | ✅ Yes (stored results)              |



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

### Temporary Tables
```aiignore
CREATE TEMP TABLE top_customers AS
SELECT *
FROM customers
WHERE spend > 1000;
```

### Materialized Views
CREATE MATERIALIZED VIEW revenue_mv AS
SELECT date, SUM(amount) AS total
FROM sales
GROUP BY date;