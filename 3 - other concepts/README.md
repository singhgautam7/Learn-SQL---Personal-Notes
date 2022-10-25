Resources -
1. [SQL interview questions](https://www.interviewbit.com/sql-interview-questions/)

## Constraints
Constraints are used to specify the rules concerning data in the table

1. **NOT NULL** - Restricts NULL value from being inserted into a column.
2. **CHECK** - Verifies that all values in a field satisfy a condition.
3. **DEFAULT** - Automatically assigns a default value if no value has been specified for the field.
4. **UNIQUE** - Ensures unique values to be inserted into the field.
5. **INDEX** - Indexes a field providing faster retrieval of records.
   1. A database index is a data structure that provides **a quick lookup of data in a column** or columns of a table.
   2. It enhances the speed of operations accessing data from a database table **at the cost of additional writes and memory** to maintain the index data structure.
6. **PRIMARY KEY** - Uniquely identifies each record in a table.
7. **FOREIGN KEY** - Ensures referential integrity for a record in another table

Example -
```sql
CREATE TABLE Persons (
    Id int AUTO_INCREMENT,
    Mobile varchar(12) UNIQUE,
    Name varchar(255) NOT NULL,
    Age int,
    City varchar(255) DEFAULT 'Raipur',
    DateRegistered TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    CHECK (Age>=18),
    PRIMARY KEY (ID)
);

CREATE INDEX idx_mobile
ON Persons (Mobile);

-- or

ALTER TABLE Persons
ADD INDEX idx_mobile (Mobile);
```


## Query and Subquery
- A **query** is a request for data or information from a database table or combination of tables.
- A **subquery** is a query within another query, also known as a nested query or inner query.


## Union, Minus, Intersect
- The **UNION** operator *combines* and returns the result-set retrieved by two or more SELECT statements.
- The **INTERSECT** operator returns *the common data* from the result-set retrieved by two or more SELECT statements.
- The **MINUS** operator *removes the deplucates* from the result-set obtained by the first SELECT statement.


## Various ways to insert
```sql
-- Bulk insert
INSERT INTO Actors
(FirstName, SecondName, DoB, Gender, MaritalStatus, NetworthInMillions)
VALUES
("Jennifer", "Aniston", "1969-11-02", "Female", "Single", 240.00),
("Angelina", "Jolie", "1975-06-04", "Female", "Single", 100.00),
("Johnny", "Depp", "1963-06-09", "Male", "Single", 200.00);

-- Using SET
INSERT INTO Actors SET DoB="1950-12-12", FirstName="Rajnikanth", SecondName="",  Gender="Male", NetWorthInMillions=50,  MaritalStatus="Married";

-- Insert NUlL or DEFAULT values
INSERT INTO Actors () VALUES ();
```

## WHERE clause operators
| Operator | Purpose |
|--|--|
| > | Greater than operator |
| >= | Greater than or equal to operator |
| < | Less than operator |
| <= | Less than or equal to operator |
| != | Not equal operator |
| <> | Not equal operator |
| <=> | NULL-safe equal to operator |
| = | Equal to operator |
| BETWEEN … AND … | Whether a value is within a range of values |
| COALESCE() | Return the first non-NULL argument |
| GREATEST() | Return the largest argument |
| IN | Whether a value is within a set of values |
| INTERVAL | Return the index of the argument that is greater than the first argument |
| IS | Test a value against a boolean |
| IS NOT | Test a value against a boolean |
| IS NOT NULL | NOT NULL value test |
| IS NULL | NULL value test |
| ISNULL() | Test whether the argument is NULL |
| LEAST() | Return the smallest argument |
| LIKE | Simple pattern matching |
| NOT BETWEEN … AND … | Whether a value is not within a range of values |
| NOT IN() | Whether a value is not within a set of values |
| NOT LIKE | Negation of simple pattern matching |
| STRCMP() | Compare two strings |


## TRUNCATE, DELETE and DROP
- **DELETE** statement is used to delete rows from a table.
- **TRUNCATE** command is used to delete all the rows from the table and free the space containing the table.
- **DROP** command is used to remove an object from the database. If you drop a table, all the rows in the table are deleted and the table structure is removed from the database.
```sql
-- Delete a specific row from the table
DELETE FROM Candidates WHERE CandidateId > 1000;

-- Delete all rows from the table
TRUNCATE TABLE Candidates;
DELETE FROM Candidates;

-- Drom the whole table
DROP TABLE Candidates;
```

## Aggregate functions
An aggregate function performs operations on a collection of values to return a single scalar value. Aggregate functions are often used with the GROUP BY and HAVING clauses of the SELECT statement. Following are the widely used SQL aggregate functions:
- **AVG()** - Calculates the mean of a collection of values.
- **COUNT()** - Counts the total number of records in a specific table or view.
- **MIN()** - Calculates the minimum of a collection of values.
- **MAX()** - Calculates the maximum of a collection of values.
- **SUM()** - Calculates the sum of a collection of values.
- **FIRST()** - Fetches the first element in a collection of values.
- **LAST()** - Fetches the last element in a collection of values.

## Scalar functions
A scalar function returns a single value based on the input value. Following are the widely used SQL scalar functions:
- **LEN()** - Calculates the total length of the given field (column).
- **UCASE()** - Converts a collection of string values to uppercase characters.
- **LCASE()** - Converts a collection of string values to lowercase characters.
- **MID()** - Extracts substrings from a collection of string values in a table.
- **CONCAT()** - Concatenates two or more strings.
- **RAND()** - Generates a random collection of numbers of a given length.
- **ROUND()** - Calculates the round-off integer value for a numeric field (or decimal point values).
- **NOW()** - Returns the current date & time.
- **FORMAT()** - Sets the format to display a collection of values.

## LEFT() and RIGHT()
- The **LEFT()** function extracts a number of characters from a string (starting from left).
  - Syntax - `LEFT(string/column, number_of_chars)`
- The **RIGHT()** function extracts a number of characters from a string (starting from right).
  - - Syntax - `RIGHT(string/column, number_of_chars)`

```sql
SELECT LEFT('SQL Tutorial', 3) AS ExtractString;
-- OUTPUT -
-- SQL

SELECT RIGHT("SQL Tutorial is cool", 4) AS ExtractString;
-- OUTPUT -
-- cool
```