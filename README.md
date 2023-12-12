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
### To exit the client, use quit or exit:
quit

exit

### For a full list of commands, use help:

help

### Connect to MySQL Server
SHOW DATABASES;

### Select Database
USE database_name;
### Show Tables
SHOW TABLES;
### Describe Table
DESCRIBE table_name;

## Database Operations

### Create Database
CREATE DATABASE database_name;

### To use a specified database:

USE database_name;

### To list all databases on the server:

SHOW DATABASES;

### Delete Database
DROP DATABASE database_name;



### Table Operations
### Create Table
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
### To list all tables in the database:

SHOW TABLES;

### Delete Table
DROP TABLE table_name;
### Alter Table (Add Column)
ALTER TABLE table_name
ADD COLUMN new_column datatype;

### Querying Data
### Select All Columns
SELECT * FROM table_name;
### Select Specific Columns
SELECT column1, column2 FROM table_name;
### Filtering and Sorting
### WHERE Clause
SELECT * FROM table_name
WHERE condition;

### ORDER BY Clause
SELECT * FROM table_name
ORDER BY column_name;

### To limit the number of rows returned:

SELECT * FROM table_name LIMIT number;

## Modifying Data in Tables
### To insert data into a table:

INSERT INTO table_name(column1, column2) VALUES(value1, value2);

### To update data in a table:
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;

### To delete data from a table:
DELETE FROM table_name WHERE condition;

### Aggregation Functions
SELECT COUNT(column_name) FROM table_name;
SELECT SUM(column_name) FROM table_name;
SELECT AVG(column_name) FROM table_name;

### Working with Functions
MySQL supports a variety of functions, including text functions, numeric functions, and date and time functions. Here are some examples:

### To concatenate strings:

SELECT CONCAT('Hello', ' ', 'World');

### To get the length of a string:

SELECT LENGTH('MySQL');

### To get the current date and time:

SELECT NOW(), CURDATE(), CURTIME();

### Working with Indexes
### To create an index on a table:

CREATE INDEX index_name ON table_name(column_name);
### To create a unique index on a table:

CREATE UNIQUE INDEX index_name ON table_name(column_name);
### To drop an index from a table:

DROP INDEX index_name ON table_name;


### Joins
### INNER JOIN
SELECT * FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;

### LEFT JOIN
SELECT * FROM table1
LEFT JOIN table2 ON table1.column_name = table2.column_name;
