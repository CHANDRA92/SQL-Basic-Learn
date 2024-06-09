## SELECT Statement

The `SELECT` statement is used to select data from a database.

- Syntax

### To Select All Fields Available in the Table

```sql
SELECT * FROM table_name;
```
### Example

```sql
SELECT * FROM customers;
```

### To Select Distinct/Unique Fields Available in the Table

```sql
SELECT DISTINCT column_name FROM table_name;
```

### Example

```sql
SELECT DISTINCT country FROM customers;
```

### To Select Specific Columns from a Table

```sql
SELECT column1, column2, column3 FROM table_name;
```

### Example

```sql
SELECT first_name, last_name, email FROM customers;
```


## The WHERE Clause

The `WHERE` clause is an essential part of SQL. It is used to filter records and fetch only those records that satisfy certain conditions.

### Basic Syntax

The basic syntax of the `WHERE` clause in an SQL `SELECT` statement is as follows:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Example with Explanation

Given the following scenario:

- **Table Name:** `students`
- **Columns:** `student_id`, `student_name`, `grade`

If you want to retrieve all students who have a grade of 'A', you would use the following SQL query:

```plsql
SELECT rollno, name, grade
FROM classroom
WHERE grade = 'A';
```


## NOTE (FOR WHERE Statement)  : 
Operators use In SQL refer :-> [[OPERATORS IN SQL]] 

```plsql
CREATE TABLE classroom (
rollno int8 PRIMARY KEY,
name varchar(50) NOT NULL,
house char(12) NOT NULL,
grade char(1) );

INSERT INTO classroom (rollno, name, house, grade)
VALUES
(1, 'Sam', 'Akash', 'B'),
(2, 'Ram', 'Agni', 'A'),
(3, 'Shyam', 'Jal', 'B'),
(4, 'Sundar', 'Agni', 'A'),
(5, 'Ram', 'Yayu', 'B');

SELECT * FROM classroom;
```

**OUTPUT:**

| rollno | name   | house | grade |
|--------|--------|-------|-------|
| 1      | Sam    | Akash | B     |
| 2      | Ram    | Agni  | A     |
| 3      | Shyam  | Jal   | B     |
| 4      | Sundar | Agni  | A     |
| 5      | Ram    | Yayu  | B     |

```plsql
SELECT rollno, name, grade
FROM classroom
WHERE grade = 'A';
```

**OUTPUT:**

| rollno | name   | grade |
|--------|--------|-------|
| 2      | Ram    | A     |
| 4      | Sundar | A     |
```plsql
SELECT * FROM classroom
WHERE grade='A' AND rollno>2;
```

| rollno | name   | grade |
|--------|--------|-------|
| 4      | Sundar | A     |


## LIMIT Clause

The `LIMIT` clause is used to set an upper limit on the number of rows returned by the SQL query.

**Stntax:** The following code will return 5 rows of data:

```sql
SELECT column_name 
FROM table_name 
LIMIT 5;
```

```plsql
SELECT * FROM customer
LIMIT 2;
```

## ORDER BY Clause

The `ORDER BY` clause is used to sort the result set in ascending (ASC) or descending (DESC) order.

**Syntax:** The following code will sort the output data by `column_name` in ascending order:

```sql
SELECT column_name 
FROM table_name 
ORDER BY column_name ASC;
```
**Example :**

```plsql
SELECT * FROM classroom
ORDER BY name ASC;
```