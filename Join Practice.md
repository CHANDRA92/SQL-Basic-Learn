
### Explanation of SQL Joins in the Image

1. **LEFT JOIN**:
   - Retrieves all records from the left table (Table A) and the matched records from the right table (Table B). The result is NULL from the right side if there is no match.
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     LEFT JOIN TableB B ON A.Key = B.Key;
     ```

2. **INNER JOIN**:
   - Retrieves records that have matching values in both tables (Table A and Table B).
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     INNER JOIN TableB B ON A.Key = B.Key;
     ```

3. **RIGHT JOIN**:
   - Retrieves all records from the right table (Table B) and the matched records from the left table (Table A). The result is NULL from the left side if there is no match.
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     RIGHT JOIN TableB B ON A.Key = B.Key;
     ```

4. **LEFT JOIN with IS NULL**:
   - Retrieves all records from the left table (Table A) where there is no match in the right table (Table B).
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     LEFT JOIN TableB B ON A.Key = B.Key
     WHERE B.Key IS NULL;
     ```

5. **RIGHT JOIN with IS NULL**:
   - Retrieves all records from the right table (Table B) where there is no match in the left table (Table A).
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     RIGHT JOIN TableB B ON A.Key = B.Key
     WHERE A.Key IS NULL;
     ```

6. **FULL OUTER JOIN**:
   - Retrieves all records when there is a match in either left (Table A) or right (Table B) table records.
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     FULL OUTER JOIN TableB B ON A.Key = B.Key;
     ```

7. **FULL OUTER JOIN with IS NULL**:
   - Retrieves all records where there is no match in either left (Table A) or right (Table B) table records.
   - **SQL Syntax**:
     ```sql
     SELECT <select_list>
     FROM TableA A
     FULL OUTER JOIN TableB B ON A.Key = B.Key
     WHERE A.Key IS NULL OR B.Key IS NULL;
     ```

### Creating Tables and Inserting Values

Here’s the SQL code to create the tables `TableA` and `TableB`, insert some values, and then you can practice the different joins:

```sql
-- Create TableA
CREATE TABLE TableA (
    ID INT PRIMARY KEY,
    Name VARCHAR(50)
);

-- Create TableB
CREATE TABLE TableB (
    ID INT PRIMARY KEY,
    Description VARCHAR(50)
);

-- Insert values into TableA
INSERT INTO TableA (ID, Name) VALUES
(1, 'Alice'),
(2, 'Bob'),
(3, 'Charlie'),
(4, 'David');

-- Insert values into TableB
INSERT INTO TableB (ID, Description) VALUES
(2, 'Engineer'),
(3, 'Doctor'),
(5, 'Lawyer');

-- LEFT JOIN
SELECT A.ID, A.Name, B.Description
FROM TableA A
LEFT JOIN TableB B ON A.ID = B.ID;

-- INNER JOIN
SELECT A.ID, A.Name, B.Description
FROM TableA A
INNER JOIN TableB B ON A.ID = B.ID;

-- RIGHT JOIN
SELECT A.ID, A.Name, B.Description
FROM TableA A
RIGHT JOIN TableB B ON A.ID = B.ID;

-- LEFT JOIN with IS NULL
SELECT A.ID, A.Name, B.Description
FROM TableA A
LEFT JOIN TableB B ON A.ID = B.ID
WHERE B.ID IS NULL;

-- RIGHT JOIN with IS NULL
SELECT A.ID, A.Name, B.Description
FROM TableA A
RIGHT JOIN TableB B ON A.ID = B.ID
WHERE A.ID IS NULL;

-- FULL OUTER JOIN
SELECT A.ID, A.Name, B.Description
FROM TableA A
FULL OUTER JOIN TableB B ON A.ID = B.ID;

-- FULL OUTER JOIN with IS NULL
SELECT A.ID, A.Name, B.Description
FROM TableA A
FULL OUTER JOIN TableB B ON A.ID = B.ID
WHERE A.ID IS NULL OR B.ID IS NULL;
```

Sure, I will format the output of each query in Markdown (md) format.

### Data in TableA
```sql
SELECT * FROM TableA;
```

| ID  | Name    |
| --- | ------- |
| 1   | Alice   |
| 2   | Bob     |
| 3   | Charlie |
| 4   | David   |

### Data in TableB
```sql
SELECT * FROM TableB;
```

| ID  | Description |
| --- | ----------- |
| 2   | Engineer    |
| 3   | Doctor      |
| 5   | Lawyer      |

### LEFT JOIN
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
LEFT JOIN TableB B ON A.ID = B.ID;
```

| ID  | Name    | Description |
| --- | ------- | ----------- |
| 1   | Alice   | NULL        |
| 2   | Bob     | Engineer    |
| 3   | Charlie | Doctor      |
| 4   | David   | NULL        |

### INNER JOIN
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
INNER JOIN TableB B ON A.ID = B.ID;
```

| ID  | Name    | Description |
| --- | ------- | ----------- |
| 2   | Bob     | Engineer    |
| 3   | Charlie | Doctor      |

### RIGHT JOIN
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
RIGHT JOIN TableB B ON A.ID = B.ID;
```

| ID  | Name    | Description |
| --- | ------- | ----------- |
| 2   | Bob     | Engineer    |
| 3   | Charlie | Doctor      |
| 5   | NULL    | Lawyer      |

### LEFT JOIN with IS NULL
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
LEFT JOIN TableB B ON A.ID = B.ID
WHERE B.ID IS NULL;
```

| ID  | Name  | Description |
| --- | ----- | ----------- |
| 1   | Alice | NULL        |
| 4   | David | NULL        |

### RIGHT JOIN with IS NULL
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
RIGHT JOIN TableB B ON A.ID = B.ID
WHERE A.ID IS NULL;
```

| ID  | Name | Description |
| --- | ---- | ----------- |
| 5   | NULL | Lawyer      |

### FULL OUTER JOIN
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
FULL OUTER JOIN TableB B ON A.ID = B.ID;
```

| ID  | Name    | Description |
| --- | ------- | ----------- |
| 1   | Alice   | NULL        |
| 2   | Bob     | Engineer    |
| 3   | Charlie | Doctor      |
| 4   | David   | NULL        |
| 5   | NULL    | Lawyer      |

### FULL OUTER JOIN with IS NULL
```sql
SELECT A.ID, A.Name, B.Description
FROM TableA A
FULL OUTER JOIN TableB B ON A.ID = B.ID
WHERE A.ID IS NULL OR B.ID IS NULL;
```

| ID  | Name  | Description |
| --- | ----- | ----------- |
| 1   | Alice | NULL        |
| 4   | David | NULL        |
| 5   | NULL  | Lawyer      |

These queries will give you the specified output and allow you to practice different types of joins in SQL.