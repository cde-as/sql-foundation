# SQL Data Summarization: Aggregate Functions, Arithmetic, and Rounding

## Aggregate Functions in SQL

### Overview of Key Aggregate Functions

1. **AVG() Function**

   - Calculates the average value of a numerical column
   - Syntax: `SELECT AVG(column_name) FROM table_name;`
   - Only works with numerical data
   - Useful for finding central tendencies in datasets

2. **SUM() Function**

   - Adds up all values in a numerical column
   - Syntax: `SELECT SUM(column_name) FROM table_name;`
   - Helpful for calculating total quantities, revenues, or budgets

3. **MIN() Function**

   - Finds the lowest value in a column
   - Works with both numerical and non-numerical data
   - Syntax: `SELECT MIN(column_name) FROM table_name;`
   - Useful for identifying minimum values across different data types

4. **MAX() Function**

   - Finds the highest value in a column
   - Compatible with numerical and non-numerical data
   - Syntax: `SELECT MAX(column_name) FROM table_name;`
   - Helpful for identifying maximum values or extreme points in a dataset

5. **COUNT() Function**
   - Counts the number of non-null records in a column
   - Can count all records or specific conditions
   - Syntax:
     - `SELECT COUNT(column_name) FROM table_name;`
     - `SELECT COUNT(*) FROM table_name;`
   - Useful for understanding dataset size and completeness

### Arithmetic in SQL Aggregate Functions

#### Basic Arithmetic Operations

- SQL supports standard arithmetic operations:
  - Addition (+)
  - Subtraction (-)
  - Multiplication (\*)
  - Division (/)

#### Example Arithmetic Queries

```sql
-- Calculate total revenue minus total cost
SELECT SUM(revenue) - SUM(cost) AS net_profit FROM financial_table;

-- Calculate average profit margin
SELECT AVG(revenue / cost * 100) AS average_profit_margin FROM financial_table;
```

## Rounding Numerical Results

### ROUND() Function

- Allows precise control over decimal places in numerical results
- Syntax: `ROUND(number, decimal_places)`
- Examples:

  ```sql
  -- Round average budget to two decimal places
  SELECT ROUND(AVG(budget), 2) AS average_film_budget FROM films;

  -- Round percentage calculations
  SELECT ROUND(SUM(revenue) / SUM(budget) * 100, 2) AS total_return_percentage FROM films;
  ```

## Aliasing in SQL

### Purpose of Aliasing

- Improves query readability
- Provides meaningful names for calculated columns
- Makes complex queries more understandable

### Aliasing Techniques

```sql
-- Column Aliasing
SELECT
    AVG(budget) AS average_budget,
    SUM(revenue) AS total_revenue,
    ROUND(AVG(revenue / budget * 100), 2) AS average_return_percentage
FROM films;
```

## Best Practices

1. Always use meaningful aliases
2. Be consistent with naming conventions
3. Use `ROUND()` to control decimal precision
4. Combine multiple aggregate functions for comprehensive insights
5. Consider the data type when applying aggregate functions

## Common Pitfalls to Avoid

- Using aggregate functions on non-compatible data types
- Forgetting to handle potential NULL values
- Overlooking the importance of clear, descriptive column names

## Learning Outcomes

- Master basic SQL aggregate functions
- Perform arithmetic calculations within SQL queries
- Use `ROUND()` to format numerical results
- Create clear, readable queries with effective aliasing
