## Inner Joins: Key Points and Examples

Table Aliasing & Column Ambiguity
When multiple tables share column names, we must specify which table we're selecting from using table.column_name syntax or aliases.

Sample Tables:

-- Books table
id | title | author_id | year
1 | The Castle | 1 | 1926
2 | Don Quixote | 2 | 1605
3 | Dune | 3 | 1965

-- Authors table
id | name | country
1 | Kafka | Czech Republic
2 | Cervantes | Spain
3 | Herbert | USA

## Using Table Aliases

-- Without aliases (longer)
SELECT books.title, authors.name, authors.country
FROM books
INNER JOIN authors
ON books.author_id = authors.id;

-- With aliases (shorter and cleaner)
SELECT b.title, a.name, a.country
FROM books b
INNER JOIN authors a
ON b.author_id = a.id;

## USING Clause Shortcut

When the joining columns have the same name, you can use the USING shortcut:
Assuming both tables use 'id' as the column name:

SELECT b.title, a.name
FROM books b
INNER JOIN authors a
USING (id);

## Common Error Example

This will cause an error because 'id' exists in both tables

SELECT id, title, name -- Error: id is ambiguous!
FROM books
INNER JOIN authors
ON books.author_id = authors.id;

-- Correct version
SELECT books.id as book_id, title, authors.name
FROM books
INNER JOIN authors
ON books.author_id = authors.id;
Best Practices

- Write JOIN statements before finalizing SELECT
- Use short, meaningful table aliases (b for books, a for authors)
- Be explicit about which table a column comes from when names are shared
- Consider using USING when column names match exactly
