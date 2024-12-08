# Order of Execution

- SQL queries are written in a certain syntactical order, however it is not processed in the way it is written.

#### 1. **FROM** Clause

- The first step is identifying and loading the base tables.
- This determines the initial data source.
- If JOINs are used, this is where table relationships are formed.

#### 2. **WHERE** Clause

- Filters individual rows before any grouping occurs.
- Applies conditions to rows from the FROM clause.
- Reduces the number of rows before further processing.

#### 3. **GROUP BY** Clause

- Groups rows that have the same values in specified columns.
- Prepares data for aggregate functions.

#### 4. **HAVING** Clause

- Filters groups after the GROUP BY clause
- Can only reference columns or aggregates from the GROUP BY.
- Similar to WHERE, but operates on grouped data.

#### 5. **SELECT** Clause

- Selects and transforms the columns.
- Determines which cloumns will be in the final output.
- Can perform calculations, use aliases, etc.

#### 6. **ORDER BY** Clause

- Sorts the final result set.
- Always the last logical operation (except LIMIT/OFFSET)

#### 7. **LIMIT/OFFSET** Clause

- The very last operation (non-logical)
- Restricts the number of rows returned

## Best practices

## - Query Writing:

i. Capitalizing SQL key words.

ii. When multiple columns are selected, some users prefer to create a new line and indent each column name for easier readability.

iii. Add semicolons at the end of queries.

### Resources:

- https://www.sqlstyle.guide/

- SQL Performance Explained by Markus Winand
