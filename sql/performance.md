### Explain

`EXPLAIN SELECT * FROM orders WHERE status = 'complete';`

### Expensive Patterns
* SELECT DISTINCT (usually bad joins)
* leading wildcards `WHERE name LIKE '%smith'`
* functions on indexed columns `WHERE LOWER(name) = 'sam'`

