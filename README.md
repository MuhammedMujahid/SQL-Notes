# SQL-Notes

## Column Constraints
Column constraints are the rules applied to the values of individual columns:

PRIMARY KEY constraint can be used to uniquely identify the row.
UNIQUE columns have a different value for every row.
NOT NULL columns must have a value.
DEFAULT assigns a default value for the column when no value is specified.
There can be only one PRIMARY KEY column per table and multiple UNIQUE columns.

```SQL
CREATE TABLE student (
  id INTEGER PRIMARY KEY,
  name TEXT UNIQUE,
  grade INTEGER NOT NULL,
  age INTEGER DEFAULT 10
);
```

## CREATE TABLE Statment
The CREATE TABLE statement creates a new table in a database. It allows one to specify the name of the table and the name of each column in the table.

```SQL

CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  column3 datatype
);
```

## INSERT Statement
The INSERT INTO statement is used to add a new record (row) to a table.

It has two forms as shown:
```SQL

Insert into columns in order.
Insert into columns by name.
-- Insert into columns in order:
INSERT INTO table_name
VALUES (value1, value2);

-- Insert into columns by name:
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

## ALTER TABLE Statement

The ALTER TABLE statement is used to modify the columns of an existing table. When combined with the ADD COLUMN clause, it is used to add a new column.
```SQL

ALTER TABLE table_name
ADD column_name datatype;
```
## DELETE Statement

The DELETE statement is used to delete records (rows) in a table. The WHERE clause specifies which record or records that should be deleted. If the WHERE clause is omitted, all records will be deleted.
```SQL

DELETE FROM table_name
WHERE some_column = some_value;
```
## UPDATE Statement

The UPDATE statement is used to edit records (rows) in a table. It includes a SET clause that indicates the column to edit and a WHERE clause for specifying the record(s).
```SQL

UPDATE table_name
SET column1 = value1, column2 = value2
WHERE some_column = some_value;
```

## AND Operator
The AND operator allows multiple conditions to be combined. Records must match both conditions that are joined by AND to be included in the result set. The given query will match any car that is blue and made after 2014.
```SQL
SELECT model
FROM cars
WHERE color = 'blue'
AND year > 2014;
```

## AS Clause
Columns or tables can be aliased using the AS clause. This allows columns or tables to be specifically renamed in the returned result set. The given query will return a result set with the column for name renamed to movie_title.

```SQL
SELECT name AS 'movie_title'
FROM movies;
```

## OR Operator
The OR operator allows multiple conditions to be combined. Records matching either condition joined by the OR are included in the result set. The given query will match customers whose state is either 'CA' or 'NY'.
```SQL
SELECT name
FROM customers
WHERE state = 'CA'
   OR state = 'NY';
```

## % Wildcard
The % wildcard can be used in a LIKE operator pattern to match zero or more unspecified character(s). The given query will match any movie that begins with The, followed by zero or more of any characters.

```SQL
SELECT name
FROM movies
WHERE name LIKE 'The%';
```

## SELECT Statement
The SELECT * statement returns all columns from the provided table in the result set. The given query will fetch all columns and records (rows) from the movies table.
```SQL
SELECT *
FROM movies;
```

## _ Wildcard
The _ wildcard can be used in a LIKE operator pattern to match any single unspecified character. The given query will match any movie which begins with a single character, followed by ove.
```SQL
SELECT name
FROM movies
WHERE name LIKE '_ove';
```

## ORDER BY Clause
The ORDER BY clause can be used to sort the result set by a particular column either alphabetically or numerically. It can be ordered in two ways:
```SQL
DESC is a keyword used to sort the results in descending order.
ASC is a keyword used to sort the results in ascending order (default).
SELECT *
FROM contacts
ORDER BY birth_date DESC;
```

## LIKE Operator
The LIKE operator can be used inside of a WHERE clause to match a specified pattern. The given query will match any movie that begins with Star in its title.
```SQL
SELECT name
FROM movies
WHERE name LIKE 'Star%';
```

## DISTINCT Clause
Unique values of a column can be selected using a DISTINCT query. For a table contact_details having five rows in which the city column contains Chicago, Madison, Boston, Madison, and Denver, the given query would return:
```SQL
Chicago
Madison
Boston
Denver
SELECT DISTINCT city
FROM contact_details;
```

## BETWEEN Operator
The BETWEEN operator can be used to filter by a range of values. The range of values can be text, numbers, or date data. The given query will match any movie made between the years 1980 and 1990, inclusive.
```SQL
SELECT *
FROM movies
WHERE year BETWEEN 1980 AND 1990;
```

## LIMIT Clause
The LIMIT clause is used to narrow, or limit, a result set to the specified number of rows. The given query will limit the result set to 5 rows.
```SQL
SELECT *
FROM movies
LIMIT 5;
```

## NULL Values
Column values can be NULL, or have no value. These records can be matched (or not matched) using the IS NULL and IS NOT NULL operators in combination with the WHERE clause. The given query will match all addresses where the address has a value or is not NULL.
```SQL
SELECT address
FROM records
WHERE address IS NOT NULL;
```

## WHERE Clause
The WHERE clause is used to filter records (rows) that match a certain condition. The given query will select all records where the pub_year equals 2017.
```SQL
SELECT title
FROM library
WHERE pub_year = 2017;
```
