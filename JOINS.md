#### 1. What is JOIN?

**JOIN** in SQL is used to combine rows from two or more tables based on a related column between them. It allows you to retrieve data from multiple tables simultaneously.

#### 2. Use of JOIN

Joins are essential in SQL for:

- Retrieving related data from multiple tables.
- Consolidating data into a single result set.
- Optimizing database queries by reducing the need for multiple queries.

#### 3. Join Types

There are several types of joins:

- **INNER JOIN**: Returns records that have matching values in both tables.
  
  Example:
  ```sql
  SELECT *
  FROM table1
  INNER JOIN table2 ON table1.column_name = table2.column_name;
  ```

- **LEFT JOIN (or LEFT OUTER JOIN)**: Returns all records from the left table and the matched records from the right table. If there is no match, NULL values are returned from the right side.
  
  Example:
  ```sql
  SELECT *
  FROM table1
  LEFT JOIN table2 ON table1.column_name = table2.column_name;
  ```

- **RIGHT JOIN (or RIGHT OUTER JOIN)**: Returns all records from the right table and the matched records from the left table. If there is no match, NULL values are returned from the left side.
  
  Example:
  ```sql
  SELECT *
  FROM table1
  RIGHT JOIN table2 ON table1.column_name = table2.column_name;
  ```

- **FULL JOIN (or FULL OUTER JOIN)**: Returns all records when there is a match in either the left or right table. If there is no match, NULL values are returned from the opposite side.
  
  Example:
  ```sql
  SELECT *
  FROM table1
  FULL JOIN table2 ON table1.column_name = table2.column_name;
  ```

- **CROSS JOIN**: Returns the Cartesian product of the two tables, i.e., all possible combinations of rows.
  
  Example:
  ```sql
  SELECT *
  FROM table1
  CROSS JOIN table2;
  ```

#### 4. Which Join to Use

- **INNER JOIN** when you only want records with matching values in both tables.
- **LEFT JOIN** or **RIGHT JOIN** when you want all records from one table and matching records from the other.
- **FULL JOIN** when you want all records from both tables.
- **CROSS JOIN** when you want to combine each row from the first table with each row from the second table (use with caution due to potentially large result sets).

#### 5. Join Syntax

The general syntax for SQL joins is:

```sql
SELECT columns
FROM table1
JOIN table2 ON table1.column_name = table2.column_name;
```

#### 6. Examples in SQL (PL/SQL)

Example 1: **INNER JOIN**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;
```

Example 2: **LEFT JOIN**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
LEFT JOIN customers ON orders.customer_id = customers.customer_id;
```

Example 3: **RIGHT JOIN**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
RIGHT JOIN customers ON orders.customer_id = customers.customer_id;
```

Example 4: **FULL JOIN**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
FULL JOIN customers ON orders.customer_id = customers.customer_id;
```

Example 5: **CROSS JOIN**

```sql
SELECT *
FROM orders
CROSS JOIN customers;
```

### Explanation

- **Example 1**: Retrieves `order_id` and `customer_name` from `orders` and `customers` tables where `customer_id` matches.
- **Example 2**: Retrieves all `order_id` from `orders` table and `customer_name` from `customers` table where `customer_id` matches, including orders without matching customers.
- **Example 3**: Retrieves all `order_id` and `customer_name` from `orders` and `customers` tables where `customer_id` matches, including customers without matching orders.
- **Example 4**: Retrieves all `order_id` and `customer_name` from `orders` and `customers` tables, whether or not there is a match between them.
- **Example 5**: Generates a Cartesian product of `orders` and `customers` tables, combining every row from `orders` with every row from `customers`.

These examples illustrate how different types of joins can be used to retrieve and combine data from related tables in SQL. Adjust `table1`, `table2`, `columns`, and `column_name` based on your specific database schema and requirements.

### JOIN CHEAT SHEET

#JoinCheatSHEET #Join

![[JoinCheatSheet.jpg]]

### Join Practice 
[[Join Practice]]