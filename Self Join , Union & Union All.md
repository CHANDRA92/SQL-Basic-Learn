## Self Join 
- A self join is a regular join in which a table is joined to itself
- **SELF Joins** are powerful for comparing values in a column of rows with the same table
- Syntax
```sql
SELECT column_name(s)
FROM Table AS T1 
JOIN Table AS T2 
ON T1.col_name = T2.col_name
```

## Union 
The SQL **UNION** clause/operator is used to combine/concatenate the results of two or more SELECT statements without returning any duplicate rows and keeps **unique records**
To use this UNION clause, each SELECT statement must have
- The same number of columns selected and expressions
- The same data type and
- Have them in the same order
- **Syntax**

```sql
SELECT column_name(s)
FROM TableA 
UNION 
SELECT column_name(s) 
FROM TableB
```
Example:

```plsql
SELECT cust_name, cust_amount
from ucusta
UNION
SELECT cust_name, cust_amount
FROM ucustb
```
## Union All
In **UNION ALL** everything is same as **UNION,** it combines/concatenate two or more table but keeps all records, **including duplicates**
- Syntax
```sql
SELECT column_name(s) 
FROM TableA
UNION ALL 
SELECT column_name(s) 
FROM TableB
```
Example :
```plsql
SELECT cust_name, cust_amount
from ucusta
UNION ALL
SELECT cust_name, cust_amount
FROM ucustb
```

## Create Table For Practice:
```plsql
INSERT INTO ucusta
VALUES
    ('Madan Mohan', 2100),
    ('Gopi Nath', 1200),
    ('Govind Dev', 5000);


CREATE TABLE IF NOT EXISTS ucustB(
    cust_name VARCHAR(50),
    cust_amount FLOAT
);

INSERT INTO ucustB VALUES
('Gopal Bhat',1500),
('Madan Mohan',2100);
```

