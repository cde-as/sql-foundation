# SQL Sorting, Grouping, and NULL Handling

## Sorting with ORDER BY Basic Sorting

The ORDER BY clause is used to sort query results in ascending or descending order.

_Ascending Order (ASC)_

_By default, results are sorted in ascending order_

- Smallest to largest for numbers
- A to Z for text
- Earliest to latest for dates

SELECT column1, column2
FROM table_name
ORDER BY column1 ASC;

_Descending Order (DESC)_

- Explicitly sorts from largest to smallest
- Z to A for text
- Latest to earliest for dates

SELECT column1, column2
FROM table_name
ORDER BY column1 DESC;
Multiple Column Sorting

You can sort by multiple columns, with each subsequent column used when previous columns have equal values:

SELECT employee_name, department, salary
FROM employees
ORDER BY department ASC, salary DESC;

### Grouping with GROUP BY

Basic Grouping

- The GROUP BY clause is used to group rows with identical values in specified columns.

SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department;

## Handling NULL Values

IS NULL and IS NOT NULL

IS NULL: Checks for NULL values
IS NOT NULL: Checks for non-NULL values

Filtering NULL Values
-- Select rows where a column is NULL
SELECT \*
FROM table_name
WHERE column_name IS NULL;

-- Select rows where a column is NOT NULL
SELECT \*
FROM table_name
WHERE column_name IS NOT NULL;

_Sorting with NULL Values_

In most databases, NULL values are treated as the lowest possible value
In ascending order, NULLs appear first
In descending order, NULLs appear last

-- Sorting with explicit NULL handling
SELECT \*
FROM employees
ORDER BY department ASC NULLS LAST;
