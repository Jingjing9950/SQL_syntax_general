# Summary

1. JOIN will combine rows from different tables if the join condition is true.
1. LEFT JOIN will return every row in the left table, and if the join condition is not met, NULL values are used to fill in the columns from the right table.
1. Primary key is a column that serves a unique identifier for the rows in the table.
1. Foreign key is a column that contains the primary key to another table.
1. CROSS JOIN lets us combine all rows of one table with all rows of another table
1. UNION stacks one dataset on top of another.
1. WITH allows us to define a bunch of temporary tables that can be used in the final query.

## eg

### JOIN multiple tables
```
SELECT * FROM orders 
JOIN subscriptions ON orders.subscription_id = subscriptions.subscription_id;

SELECT * FROM orders 
JOIN subscriptions ON orders.subscription_id = subscriptions.subscription_id 
WHERE subscriptions.description = 'Fashion Magazine';
```

### INNER JOIN
```
SELECT count(*) FROM newspaper
JOIN online ON newspaper.id = online.id;
```

### LEFT JOIN will keep all rows from the fisrt table
```
SELECT * FROM newspaper
LEFT JOIN online ON newspaper.id = online.id
WHERE online.id IS NULL;
```

### CROSS JOIN to combie all rows of one table with all rows of another table
```
SELECT month, count(*) as subscribers
FROM newspaper
CROSS JOIN months
WHERE start_month < month AND end_month > month
GROUP BY month;
```

### UNION to stack one dataset on the top of the other
```
SELECT * FROM newspaper
UNION 
SELECT * FROM online;
```


### WITH combine two tables but one of the tables is the result of another calculation
```
WITH previous_results AS (
SELECT customer_id, count(subscription_id) as subscriptions FROM orders GROUP BY customer_id)
SELECT customers.customer_name, previous_results.subscriptions FROM previous_results 
JOIN customers ON customers.customer_id = previous_results.customer_id;
```