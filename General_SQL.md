# General SQL key word:
1. CREATE TABLE creates a new table.
1. INSERT INTO adds a new row to a table.
1. SELECT queries data from a table.
1. UPDATE edits a row in a table.
1. ALTER TABLE changes an existing table.
1. DELETE FROM deletes rows from a table.

## eg.
### SELECT clause
```
SELECT * FROM celebs;
```

### CREATE new tables
```
CREATE TABLE table_name (
   column_1 data_type, 
   column_2 data_type, 
   column_3 data_type
);
```


### INSERT values to a table
```
INSERT INTO celebs (id, name, age) VALUES (1, 'Justin Bieber', 21);
```

### Change value of row
```
UPDATE celebs 
SET age = 22 
WHERE id = 1; 
```
### ADD a new column into a table
```
ALTER TABLE celebs ADD COLUMN twitter_handle TEXT; 
```

### DELETE rows with conditions
```
DELETE FROM celebs WHERE twitter_handle IS NULL; 
```

### Constraints with column value
```REATE TABLE celebs (
   id INTEGER PRIMARY KEY, 
   name TEXT UNIQUE,
   date_of_birth TEXT NOT NULL,
   date_of_death TEXT DEFAULT 'Not Applicable',
);
```
