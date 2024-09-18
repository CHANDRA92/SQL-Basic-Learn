In SQL, joins are used to combine rows from two or more tables based on a related column between them. Here are the main types of joins in SQL:

1. **INNER JOIN**:
   - Returns records that have matching values in both tables.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     INNER JOIN table2 b ON a.common_field = b.common_field;
     ```

2. **LEFT JOIN (or LEFT OUTER JOIN)**:
   - Returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side if there is no match.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     LEFT JOIN table2 b ON a.common_field = b.common_field;
     ```

3. **RIGHT JOIN (or RIGHT OUTER JOIN)**:
   - Returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side when there is no match.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     RIGHT JOIN table2 b ON a.common_field = b.common_field;
     ```

4. **FULL JOIN (or FULL OUTER JOIN)**:
   - Returns all records when there is a match in either left (table1) or right (table2) table records. If there is no match, the result is NULL on the side that doesn't have a match.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     FULL JOIN table2 b ON a.common_field = b.common_field;
     ```

5. **CROSS JOIN**:
   - Returns the Cartesian product of the two tables, meaning it will return all possible combinations of rows.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     CROSS JOIN table2 b;
     ```

6. **SELF JOIN**:
   - Joins a table to itself. This is useful for comparing rows within the same table.
   - Example:
     ```sql
     SELECT a.column1, b.column2
     FROM table1 a
     INNER JOIN table1 b ON a.common_field = b.common_field;
     ```

Each of these joins serves a different purpose and is useful for different types of queries and data relationships.