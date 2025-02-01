## Multiple Joins in SQL: Fundamentals

Understanding Join Types and Conditions:

### ON Clause

- Used when joining tables with different column names
- Provides flexibility for complex join conditions
- Best for custom join conditions

-- Example: Joining movies with directors
SELECT m.title, d.name
FROM movies m
JOIN directors d ON m.director_id = d.id;

### USING Clause

- Used when tables share identical column names
- Shorter, cleaner syntax
- Less flexible than ON
- Cannot be used when joining columns have different names

-- Example: When both tables have 'movie_id'
SELECT m.title, r.rating
FROM movies m
JOIN ratings r USING(movie_id);

### AND Clause in Joins

- Adds additional filtering conditions to the join
- Filters data DURING the join (not after)
- Different from WHERE clause which filters AFTER the join

-- Example: Filtering while joining
SELECT m.title, d.name
FROM movies m
JOIN directors d
ON m.director_id = d.id
AND d.country = 'USA'
AND m.year > 2000;
