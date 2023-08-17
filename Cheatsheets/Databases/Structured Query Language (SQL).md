## Basic SQL Commands

```sql
-- Create a new database
CREATE DATABASE database_name;

-- Use a database
USE database_name;

-- Create a new table
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  ...
);

-- Insert data into a table
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);

-- Select data from a table
SELECT column1, column2 FROM table_name WHERE condition;

-- Update data in a table
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;

-- Delete data from a table
DELETE FROM table_name WHERE condition;
```
## Querying Data

```sql
-- Select all columns from a table
SELECT * FROM table_name;

-- Filtering results
SELECT column1, column2 FROM table_name WHERE column3 = value;

-- Ordering results
SELECT * FROM table_name ORDER BY column_name ASC/DESC;

-- Limiting results
SELECT * FROM table_name LIMIT number;

-- Joining tables
SELECT * FROM table1 JOIN table2 ON table1.column = table2.column;
```

## Aggregating Data

```sql
-- Count rows
SELECT COUNT(*) FROM table_name;

-- Calculate average
SELECT AVG(column_name) FROM table_name;

-- Find maximum/minimum
SELECT MAX(column_name), MIN(column_name) FROM table_name;

-- Sum values
SELECT SUM(column_name) FROM table_name;
```

## Grouping and Filtering Aggregates

```sql
SELECT column1, AVG(column2) FROM table_name GROUP BY column1;

SELECT column1, AVG(column2) FROM table_name GROUP BY column1 HAVING AVG(column2) > value;
```

## Advanced Queries

```sql
-- Subqueries
SELECT column1 FROM table_name WHERE column2 IN (SELECT column3 FROM another_table);

-- Common Table Expressions (CTEs)
WITH cte_name AS (
  SELECT ...
)
SELECT * FROM cte_name;

-- Window Functions
SELECT column1, column2, ROW_NUMBER() OVER (PARTITION BY column1 ORDER BY column2) AS row_num FROM table_name;
```

## Indexing

```sql
-- Create an index
CREATE INDEX index_name ON table_name (column_name);

-- Remove an index
DROP INDEX index_name ON table_name;
```

## Constraints

```sql
-- Primary key
CREATE TABLE table_name (
  id INT PRIMARY KEY,
  ...
);

-- Foreign key
CREATE TABLE orders (
  order_id INT PRIMARY KEY,
  customer_id INT,
  FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```

## Transactions

```sql
-- Start a transaction
BEGIN;

-- Commit changes
COMMIT;

-- Rollback changes
ROLLBACK;
```

## Views

```sql
-- Create a view
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;

-- Use a view
SELECT * FROM view_name;
```

## Joins

```sql
-- Inner Join
SELECT * FROM customers
INNER JOIN orders ON customers.customer_id = orders.customer_id;

-- Left Join
SELECT * FROM customers
LEFT JOIN orders ON customers.customer_id = orders.customer_id;

-- Right Join
SELECT * FROM customers
RIGHT JOIN orders ON customers.customer_id = orders.customer_id;
```

# Advanced

## Subqueries

```sql
-- Correlated subquery
SELECT column1 FROM table1 WHERE column2 = (SELECT MAX(column2) FROM table2 WHERE table1.id = table2.id);
```

## Common Table Expressions (CTEs)

```sql
-- Recursive CTE
WITH RECURSIVE cte_name AS (
  SELECT initial_query
  UNION
  SELECT recursive_query FROM cte_name WHERE condition
)
SELECT * FROM cte_name;
```

## Window Functions

```sql
-- Calculate running total
SELECT column1, column2, SUM(column2) OVER (ORDER BY column1) AS running_total FROM table_name;

-- Ranking
SELECT column1, column2, RANK() OVER (PARTITION BY column3 ORDER BY column2 DESC) AS rank FROM table_name;
```

## Pivot and Unpivot

```sql
-- Pivot
SELECT *
FROM table_name
PIVOT (aggregate_function(column2) FOR column3 IN (value1, value2, ...));

-- Unpivot
SELECT column1, column2, column3
FROM (SELECT * FROM table_name) AS source
UNPIVOT (column2 FOR column3 IN (value1, value2, ...)) AS unpivoted;
```

## JSON Functions

```sql
-- Extract value from JSON
SELECT column1->>'$.key' FROM table_name;

-- Query JSON object
SELECT * FROM table_name WHERE column1 @> '{"key": "value"}';
```

## Full-Text Search

```sql
-- Creating full-text index
CREATE INDEX index_name ON table_name USING gin(to_tsvector('english', column_name));

-- Using full-text search
SELECT * FROM table_name WHERE to_tsvector('english', column_name) @@ to_tsquery('search_term');
```

## Temporal Tables (SQL:2011)

```sql
-- Create a system-versioned table
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  ...,
  SYSTEM VERSIONING
);

-- Query historical data
SELECT * FROM table_name FOR SYSTEM_TIME BETWEEN start_time AND end_time;
```

## Materialized Views

```sql
-- Create a materialized view
CREATE MATERIALIZED VIEW mv_name AS
SELECT column1, column2 FROM table_name WHERE condition;

-- Refresh materialized view
REFRESH MATERIALIZED VIEW mv_name;
```

## Stored Procedures

```sql
-- Create a stored procedure
CREATE PROCEDURE procedure_name (parameter1 datatype, parameter2 datatype)
BEGIN
  -- procedure logic
END;

-- Call a stored procedure
CALL procedure_name(value1, value2);
```

## Triggers

```sql
-- Create a stored procedure
CREATE PROCEDURE procedure_name (parameter1 datatype, parameter2 datatype)
BEGIN
  -- procedure logic
END;

-- Call a stored procedure
CALL procedure_name(value1, value2);
```

## User-Defined Functions

```sql
-- Create a user-defined function
CREATE FUNCTION function_name (parameter datatype)
RETURNS return_type
BEGIN
  -- function logic
  RETURN value;
END;

-- Call a user-defined function
SELECT function_name(value);
```

## User-Defined Types

```sql
-- Create a user-defined type
CREATE TYPE type_name AS (column1 datatype, column2 datatype, ...);

-- Use user-defined type
CREATE TABLE table_name (
  column1 type_name,
  ...
);
```

>[!Note]
>This advanced SQL cheat-sheet covers more intricate features and concepts of SQL.

#databases