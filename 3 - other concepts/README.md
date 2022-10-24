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
    Id int,
    Mobile varchar(12) UNIQUE,
    Name varchar(255) NOT NULL,
    Age int,
    City varchar(255) DEFAULT 'Raipur',
    CHECK (Age>=18),
    PRIMARY KEY (ID)
);

CREATE INDEX idx_mobile
ON Persons (Mobile);
```


## Query and Subquery
- A **query** is a request for data or information from a database table or combination of tables.
- A **subquery** is a query within another query, also known as a nested query or inner query.


## Union, Minus, Intersect
- The **UNION** operator *combines* and returns the result-set retrieved by two or more SELECT statements.
- The **INTERSECT** operator returns *the common data* from the result-set retrieved by two or more SELECT statements.
- The **MINUS** operator *removes the deplucates* from the result-set obtained by the first SELECT statement.