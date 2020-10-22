# SQL 

Structured Query Language, or SQL, allows users to query, manipulate, and transform data from a database. 

## Lesson 1: Select Queries 

We can use the `SELECT` statements, or commonly known as queries, to find what data we are looking for, where to find it, and to transform it before it is being returned. 

We can select a query by a specific column by inputting 
```
SELECT column1, column2 FROM mytable;
```
If we want to search all columns, we enter 
```
SELECT * FROM mytable;
``` 

## Lesson 2: Queries with Constraints

Sifting through data can be tendious. In order to make our lives easier, we use the `WHERE` statement. 

|  Operator | Condition | SQL Example | 
|---|---|---|
|  =, !=, < <=, >, >= | Standard numerical operators  | col_name != 4  |  
| BETWEEN … AND …  | Number is within range of two values (inclusive)  |   col_name BETWEEN 1.5 AND 10.5 |   
| NOT BETWEEN … AND …  | Number is not within range of two values (inclusive)  |  col_name NOT BETWEEN 1 AND 10 |   
| IN (…)|Number exists in a list | col_name IN (2, 4, 6)|
| NOT IN (…) | Number does not exist in a list | col_name NOT IN (1, 3, 5) |

## Lesson 3: Queries with Constraints 

We make the queries more strict such as having case-sensitive comparisons. Some of the common ones are showed below: 

|  Operator | Condition | SQL Example |
|---|---|---|
| =	| Case sensitive exact string comparison (notice the single equals) | 	col_name = "abc" |
| != or <> |	Case sensitive exact string inequality comparison	|col_name != "abcd" |
| LIKE | Case insensitive exact string comparison	| col_name LIKE "ABC" | 
| NOT LIKE |	Case insensitive exact string inequality comparison	|col_name NOT LIKE "ABCD" | 
|% |	Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE)	| col_name LIKE "%AT%"(matches "AT", "ATTIC", "CAT" or even "BATS") |
| _	 |Used anywhere in a string to match a single character (only with LIKE or NOT LIKE) |	col_name LIKE "AN_"(matches "AND", but not "AN") |
| IN (…) | String exists in a list	|col_name IN ("A", "B", "C") | 
| NOT IN (…) | 	String does not exist in a list | 	col_name NOT IN ("D", "E", "F") |

## Lesson 4: Filtering and Sorting Query Results

We can use the `DISTINCT` keyword to take out duplicate columns in our queries. 

`ORDER BY` sorts the data in ascending or descending order. 

## Lesson 13: Inserting Rows 

If we want to add rows with values, we can do so by running the command below: 

```
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
       (value_or_expr_2, another_value_or_expr_2, …),
       …;
```

## Lesson 14: Updating Rows

Example: 

```
UPDATE movies
SET director = "John Lasseter"
WHERE id = 2;
```
## Lesson 15: Deleting Rows

Example 
```
DELETE FROM mytable
WHERE condition;
```

## Lesson 16: Creating Tables 

Example: 

```
CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    director TEXT,
    year INTEGER, 
    length_minutes INTEGER
);
```

## Lesson 17: Altering Tables 

To add columns:

```
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint 
    DEFAULT default_value;
```

To remove columns:

```
ALTER TABLE mytable
DROP column_to_be_deleted;
```

To rename the table:
```
ALTER TABLE mytable
RENAME TO new_table_name;
```

# Lesson 18: Dropping tables

This is similar to delete, but it also gets rid of the schema from the database. 

Example:

```
DROP TABLE IF EXISTS mytable;
```

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)
