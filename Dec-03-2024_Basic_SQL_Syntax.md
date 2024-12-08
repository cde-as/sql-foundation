# SELECT Statement

- SELECT is used to retrieve data from one or more tables in a database.
- SELECT \* retrieves all columns from a table.
- SELECT DISTINCT is used to return only unique values, eliminating duplicate rows.

# Views

- A view is a virtual table based on the result of a SQL query.
- Note: Resulting data does not get stored in the server. Always shows up-to-date data when queried.
- Syntax:
  CREATE VIEW view_name AS
  SELECT column1 ...
  FROM...;

# Aliasing

- Aliasing is used to rename columns or tables to:
  Improve readability
  Simplify complex queries
  Provide more meaningful column names

- Syntax: SELECT column_name AS alias_name

# Aggregate Functions

- COUNT(): Returns the number of rows that matches a specific criteria.
- COUNT(\*): Counts all rows in a table
- COUNT(column_name) counts non-null values in a specific column
- If we want to count multiple columns we have to use COUNT() multiple times

Example: 
SELECT COUNT(language) AS count_languages, COUNT(country) AS count_countries
FROM films;

- Using the DISTINCT keyword removes duplicate values.

Example: 
SELECT COUNT(DISTINCT language) AS count_distinct_language 
FROM films;