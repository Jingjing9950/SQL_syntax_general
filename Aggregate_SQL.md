# Summary
1. COUNT: count the number of rows
1. SUM: the sum of the values in a column
1. MAX/MIN: the largest/smallest value
1. AVG: the average of the values in a column
1. ROUND: round the values in the column

## eg

### COUNT to count the nuumbers 
```
SELECT count(*) AS free FROM fake_apps WHERE price = 0.0;
```


### SUM to sum up all the values in a column
```
SELECT id, name, SUM(downloads) AS count FROM fake_apps;
```


### MAX or MIN to return the highest or lowest values in a column
```
SELECT name, MAX(price) FROM fake_apps;
```


### AVERAGE to calculate the average number of a column
```
SELECT AVG(price) FROM fake_apps;
```


### ROUND
```
SELECT ROUND(AVG(price), 2) FROM fake_apps;
```


### GROUP BY to calculate an aggregate for data with certain characteristics
```
SELECT category, SUM(downloads) FROM fake_apps GROUP BY category;
(The GROUP BY statement comes after any WHERE statements, but before ORDER BY or LIMIT.)
```

```
SELECT ROUND(imdb_rating),
   COUNT(name)
FROM movies
GROUP BY 1
ORDER BY 1;
(Here, the 1 refers to the first column in our SELECT statement, ROUND(imdb_rating).
```


### HAVING
```
SELECT price, ROUND(AVG(downloads)) FROM fake_apps GROUP BY price HAVING count(*) > 9;
(SELECT price, ROUND(AVG(downloads)) FROM fake_apps GROUP BY price HAVING count(*) > 9;)
(When we want to limit the results of a query based on an aggregate property, use HAVING.)
(HAVING statement always comes after GROUP BY, but before ORDER BY and LIMIT.)
```

