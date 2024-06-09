**The CREATE TABLE statement is used to create a new table in a database**
* Syntax
```sql
CREATE TABLE table_name
(
	column_namel datatype constraint,
	column_name2 datatype constraint,
	column_name3 datatype constraint,
);
```

* Example
```sql
CREATE TABLE customer
(
	ID int8 PRIMARY KEY,
	Name varchar(50) NOT NULL,
	City varchar(50),
	Salary numeric
);
```

**For View Table :**
```sql
SELECT * FROM customer;
```
