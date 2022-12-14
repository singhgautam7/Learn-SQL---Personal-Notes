## Show db version
```sql
SELECT VERSION();
```

## Select database
```sql
USE lion;
```

## Delete table
```sql
DROP TABLE student;
```

## Create student table
```sql
CREATE TABLE student(
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(20) NOT NULL UNIQUE,
    major VARCHAR(20) DEFAULT 'undecided'
);
```

## Describe student
```sql
DESCRIBE student;
```

## Update table and add or delete column
```sql
ALTER TABLE student DROP gpa;
ALTER TABLE student ADD gpa DECIMAL(3,2);
ALTER TABLE student MODIFY major VARCHAR(20) NULL;
```

## Adding data in databas
```sql
-- INSERT INTO student VALUES(1, 'Jack', 'Biology');
INSERT INTO student(name, major) VALUES('Jack', 'Biology');
INSERT INTO student(name, major) VALUES('Kate', 'Socialogy');
INSERT INTO student(name, major) VALUES('Claire', 'Chemistry');
```

## Update the row
```sql
UPDATE student SET major = 'Bio' where major='Biology';
UPDATE student SET name = 'Tom', major = 'Chemistry' where student_id=1;
```

## Delete a row
```sql
DELETE FROM student WHERE student_id=5;
```

## See rows in table
```sql
SELECT * FROM student;
SELECT name, major FROM student;
SELECT student.name, student.major FROM student;
SELECT student.name, student.major FROM student ORDER BY name;
SELECT student.name, student.major FROM student ORDER BY name DESC LIMIT 2;
SELECT * FROM student WHERE major = 'Chemistry' or major = 'Bio';
SELECT * FROM student WHERE name IN ('Claire', 'Kate');
```