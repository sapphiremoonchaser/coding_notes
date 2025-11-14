# Optimization

### Expensive Patterns
* SELECT DISTINCT (usually bad joins)
* leading wildcards `WHERE name LIKE '%smith'`
* functions on indexed columns `WHERE LOWER(name) = 'sam'`

### Use Proper Indexing

#### Good columns for indexing:
* Columns with `JOIN` conditions
* Columns in `WHERE` filters
* Columns sorted in `ORDER BY`
* Columns with lots of unique values

#### Avoid Indexing
* very low-cardinality columns
* columns that change constantly

### Use `EXPLAIN` to Understand Query Plans

#### Red Flags
* Full table scans
* Costly nested loops
* Large sorts or hash aggregations
* Missing indexes


### Filter Early

### Avoid functions on indexed columns

### Reduce `DISTINCT` use
* fix the join condition
* remove unnecessary columns

### Replace Correlated Subqueries with Joins

#### Correlated Subquery
```aiignore
SELECT name
FROM customers c
WHERE spend > (SELECT AVG(spend) FROM orders o WHERE o.c_id = c.id);
```

#### Using Join instead
```aiignore
SELECT c.name
FROM customers c
JOIN (
    SELECT c_id, AVG(spend) AS avg_spend
    FROM orders
    GROUP BY c_id
) x ON c.id = x.c_id
WHERE c.spend > x.avg_spend;
```

### Use Window Functions instead of Self-Joins

#### Self-join
```aiignore
SELECT a.id, a.sales, b.sales AS prev_sales
FROM sales a
LEFT JOIN sales b ON a.date = b.date + 1;
```

#### Window Fuction
```aiignore
SELECT date, sales, LAG(sales) OVER (ORDER BY date) AS prev_sales
FROM sales;
```