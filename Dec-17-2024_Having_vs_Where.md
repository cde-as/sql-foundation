# Having Clause Vs. Where Clause

In SQL, we cannot filter aggregate functions using the _WHERE_ clause.
If we want to filter based on a result of an aggregate function we use the clause _HAVING_.

### Fundamental Distinction

- _WHERE_ filters individual records before grouping and aggregation
- \*HAVING+ filters grouped records after aggregation has occurred

Theory:

- The reason why GROUPS have their own word is due to the order of execution.
  -- Order of execution:

1. FROM: Identify the table(s)
2. WHERE: Filter individual rows
3. GROUP BY: Create groups
4. HAVING: Filter groups based on aggregate conditions
5. SELECT: Choose columns
6. ORDER BY: Sort the results
7. LIMIT: Restrict number of rows returned

By reviewing this order we can see that WHERE is executed before GROUP BY and before any aggregation occurs.

This also shows us why we can use aliases in ORDER BY since it is after SELECT, but we cannot use aliases for HAVING as it is after SELECT.

### Having vs. Where

- WHERE filters individual records, HAVING filters grouped records.

_Example 1: Basic Filtering_
-- Using WHERE to filter individual records
SELECT department, salary
FROM employees
WHERE department = 'Sales';

-- Using HAVING to filter grouped results
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;

_Example 2: Complex Filtering_
-- Find departments with more than 5 employees
-- and total salary greater than $500,000
SELECT department,
COUNT(_) as employee_count,
SUM(salary) as total_department_salary
FROM employees
WHERE hire_date > '2020-01-01' -- Filter individual rows
GROUP BY department
HAVING COUNT(_) > 5 AND SUM(salary) > 500000;
