# Summary:
1. SELECT is the clause we use every time we want to query information from a database.
1. AS renames a column or table.
1. DISTINCT return unique values.
1. WHERE is a popular command that lets you filter the results of the query based on conditions that you specify.
1. LIKE and BETWEEN are special operators.
1. AND and OR combines multiple conditions.
1. ORDER BY sorts the result.
1. LIMIT specifies the maximum number of rows that the query will return.
1. CASE creates different outputs.

## eg.
### SELECT columns from a table
```
SELECT name, genre, year FROM movies;
```


### AS Rename a column name
```
SELECT imdb_rating as IMDb 
FROM movies;
```


### DISTINCT return unique values, filter out all duplicate values in a specific column(s)
```
SELECT DISTINCT year
FROM movies;
```


### WHERE filter column(s) with conditions
```
SELECT * FROM movies
WHERE year >2014;
```


### LIKE search for a specific pattern in a column
```
SELECT * FROM movies
WHERE name LIKE "se_en"; 
("_" is wildcard used to substitute any individual character)

SELECT * 
FROM movies
WHERE name LIKE 'A%';
("%" is wildcard used to match missiong letters in the pattern, "A%" matchs all names begin with letter "A")

SELECT * 
FROM movies
WHERE name LIKE '%a';
("%a" matchs all names end with "a")

SELECT * 
FROM movies 
WHERE name LIKE '%man%';
("man% matchs all names contain "man")
```


### IS NULL & IS NOT NULL are conditions
```
SELECT name
FROM movies 
WHERE imdb_rating IS NOT NULL;
```


### BETWEEN AND used to filter with conditions
```
SELECT *
FROM movies
WHERE name BETWEEN 'A' AND 'J';

SELECT *
FROM movies
WHERE year BETWEEN 1990 AND 1999;
```


### AND to combine two conditions
```
SELECT * FROM movies WHERE year < 1985 AND genre = "horror";
```


### OR to display reault if any condition is true
```
SELECT *
FROM movies
WHERE year > 2014
   OR genre = 'action';
```


### ORDER BY to sort the result
```
SELECT *
FROM movies
WHERE imdb_rating > 8
ORDER BY year DESC;
(DESC or ASC is key word used to sort the result in orders)
```


### LIMIT used to limit the maximum number of rows to be displayed
```
SELECT * FROM movies ORDER BY imdb_rating DESC LIMIT 3;
```


### CASE used to allow user to create different outputs
```
SELECT name,
CASE 
WHEN genre = "romance" THEN "Fun"
WHEN genre = "comedy" THEN "Fun"
ELSE "Serious"
END AS "Mood"
FROM movies;
```
