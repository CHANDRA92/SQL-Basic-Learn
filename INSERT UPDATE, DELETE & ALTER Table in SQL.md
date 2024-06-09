## The Insert Into statement is used to insert new records in a table

- Syntax :
```plsql
INSERT INTO TABLE_NAME
(col1, col2, colN):
VALUES
(val1, val2 val N);
```
- Example
```plsql
INSERT INTO customer
(ID,Name,City,Salary)
VALUES
(1,'Ram','Delhi',1500),
(2,'Sam','ASN',100),
(3,'Yam','PRR',9500),
(4,'Tom','ADA',7000);
```

**Result :**

| ID  | Name | City  | Salary |
| --- | ---- | ----- | ------ |
| 1   | Ram  | Delhi | 1500   |
| 2   | Sam  | ASN   | 100    |
| 3   | Yam  | PRR   | 9500   |
| 4   | Tom  | ADA   | 7000   |

## The UPDATE command is used to update  existing a table
- Syntax :
```plsql
UPDATE TABLE_NAME
SET "Col_nam1" = 'Val1', "Col_nam2" = 'Val2'
Where ID = 'Valie';
```
- Example:
```plsql
UPDATE customer
SET name='Sam', salary=210
WHERE id=4;
```

| ID  | Name | City  | Salary |
| --- | ---- | ----- | ------ |
| 1   | Ram  | Delhi | 1500   |
| 2   | Sam  | ASN   | 100    |
| 3   | Yam  | PRR   | 9500   |
| 4   | Sam  | ADA   | 210    |

## Delete Values In Table 

The <ins>DELETE</ins> statement is used to delete existing record in a table
- Syntax
```plsql
DELETE FROM table_name WHERE condition;
```
- Example
```plsql
DELETE FROM customer
WHERE ID=3;
```
```output
DELETE 1 successfully
```

## ALTER Table

The <ins> ALTER TABLE </ins> statement is used to add, delete, or modify columns in an existing table
- **ALTER TABLE - ADD Column Syntax**
	<span style="color:#00b0f0">ALTER TABLE  
</span>  table_name
	<span style="color:#FF0000">ADD COLUMN</span>  column_name

```plsql
	ALTER TABLE customer
	ADD COLUMN age INTEGER;
	
	```

- **ALTER TABLE - DROP Column Syntax**
	<span style="color:#00b0f0">ALTER TABLE  
</span>  table_name
	<span style="color:#FF0000"> DROP COLUMN</span>  column_name
	```plsql
	ALTER TABLE customer
	DROP COLUMN age;
```
	
	
-  **ALTER TABLE - ALTER/MODIFY Column Syntax**
	<span style="color:#00b0f0">ALTER TABLE  
</span>  table_name
	<span style="color:#FF0000">ALTER COLUMN</span>  column_name datatype;
	```plsql
	ALTER TABLE customer
	RENAME COLUMN ID TO cusId;
```

## DROP & TRUNCATE Table
The DROP TABLE command deletes a table in the database 
- Syntax
```plsql
DROP TABLE table_name;
```

The TRUNCATE TABLE command deletes the data inside a table, but not the table itself
- Syntax 
```plsql
TRUNCATE TABLE table_name;
```
