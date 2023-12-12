# MySQL Guide and Cheatsheet

## Table of Contents

1. [Introduction](#introduction)
2. [Basic Commands](#basic-commands)
3. [Database Operations](#database-operations)
4. [Table Operations](#table-operations)
5. [Querying Data](#querying-data)
6. [Filtering and Sorting](#filtering-and-sorting)
7. [Aggregation Functions](#aggregation-functions)
8. [Joins](#joins)

## Introduction

MySQL is a popular relational database management system. This guide provides a cheatsheet for basic to advanced MySQL commands.

## Basic Commands

### Connect to MySQL Server

```sql
mysql -h hostname -u username -p
```

### To exit the client, use quit or exit

```sql
quit
```

```sql

exit
```

### For a full list of commands, use help

```sql
help

```

### Comments

```sql 
-- This is a single line comment

/*
This is a 
multi-line comment
*/
```

### Show databases

```sql
SHOW DATABASES;

```

### Select Database

```sql
USE database_name;

```

### Show Tables

```sql
SHOW TABLES;

```

### Describe Table

```sql
DESCRIBE table_name;

```

## Database Operations

### Create Database

```sql
CREATE DATABASE database_name;

```

### To use a specified database

```sql
USE database_name;

```

### To list all databases on the server

```sql
SHOW DATABASES;

```

### Delete Database

```sql
DROP DATABASE database_name;

```

### Table Operations

### Create Table

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);

```

### To list all tables in the database

```sql
SHOW TABLES;

```

### Delete Table

```sql
DROP TABLE table_name;

```

### Alter Table (Add Column)

```sql
ALTER TABLE table_name
ADD COLUMN new_column datatype;
```

### Querying Data

### Select All Columns

```sql
SELECT * FROM table_name;

```

### Select Specific Columns

```sql
SELECT column1, column2 FROM table_name;

```

### Filtering and Sorting

### WHERE Clause

```sql
SELECT * FROM table_name
WHERE condition;
```

### ORDER BY Clause

```sql
SELECT * FROM table_name
ORDER BY column_name;
```

### To limit the number of rows returned

```sql
SELECT * FROM table_name LIMIT number;

```

## Modifying Data in Tables

### To insert data into a table

```sql
INSERT INTO table_name(column1, column2) VALUES(value1, value2);

```

### To update data in a table

```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;

```

### To delete data from a table

```sql
DELETE FROM table_name WHERE condition;
```

### Aggregation Functions

```sql
SELECT COUNT(column_name) FROM table_name; -- Count
SELECT SUM(column_name) FROM table_name; -- Sum
SELECT AVG(column_name) FROM table_name; -- Average
SELECT MIN(column_name) FROM table_name; -- Minimum
SELECT MAX(column_name) FROM table_name; -- Maximum
```

### Working with Functions

MySQL supports a variety of functions, including text functions, numeric functions, and date and time functions. Here are some examples:

### To concatenate strings

```sql
SELECT CONCAT('Hello', ' ', 'World');

```

### To get the length of a string

```sql
SELECT LENGTH('MySQL');

```

### Math

```sql
SELECT ABS(column_name) FROM table_name; -- Absolute value
SELECT ROUND(column_name, decimals) FROM table_name; -- Round value
SELECT CEILING(column_name) FROM table_name; -- Round up value
SELECT FLOOR(column_name) FROM table_name; -- Round down value```

### To get the current date and time

```sql
SELECT NOW(), CURDATE(), CURTIME();

```

### Working with Indexes

### To create an index on a table

```sql
CREATE INDEX index_name ON table_name(column_name);

```

### To create a unique index on a table

```sql

CREATE UNIQUE INDEX index_name ON table_name(column_name);

```

### To drop an index from a table

```sql
DROP INDEX index_name ON table_name;

```

### Joins

### INNER JOIN

```sql
SELECT * FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;
```

### LEFT JOIN

```sql
SELECT * FROM table1
LEFT JOIN table2 ON table1.column_name = table2.column_name;
```

### RIGHT JOIN

```sql
SELECT * FROM table1
RIGHT JOIN table2 ON table1.column_name = table2.column_name;
```

### FULL OUTER JOIN

```sql
SELECT * FROM table1
FULL OUTER JOIN table2 ON table1.column_name = table2.column_name;

```

### UNION

```sql
SELECT column_name FROM table1
UNION
SELECT column_name FROM table2;
```

### UNION ALL

```sql
SELECT column_name FROM table1
UNION ALL
SELECT column_name FROM table2;
```

## VIEWS

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

## Group by

```sql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name;
```

## Having

```sql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name
HAVING COUNT(*) > 1;
```

## Subqueries

```sql
SELECT column_name 
FROM table_name
WHERE column_name IN (SELECT column_name FROM table_name WHERE condition);
```

### Wildcards

```sql
SELECT * FROM table_name
WHERE column_name LIKE 'a%'; -- Starts with "a"
```

### Case

```sql
SELECT column_name,
CASE 
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ELSE result
END 
FROM table_name;
```

### Coalesce

```sql
SELECT COALESCE(column_name, 'N/A') 
FROM table_name;
```

### Null

```sql
SELECT ISNULL(column_name, 'N/A') 
FROM table_name;
```

### Full-text search

```sql
SELECT * FROM table_name
WHERE CONTAINS(column_name, 'search_term');
```