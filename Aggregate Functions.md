# Note : -[PostgreSQL Aggregate Functions Documentation](https://www.postgresql.org/docs/9.0/functions-aggregate.html)
# Most Used Aggregate Functions

Aggregate functions perform calculations on multiple values and return a single value. They are often used with `GROUP BY` and `SELECT` statements.

## `COUNT()`: Returns the Number of Values

Returns the number of rows (or non-null values) in a result set.

```sql
SELECT COUNT(*) AS total_rows FROM table_name;

SELECT COUNT(*) FROM ecomcustomer;
```

## `SUM()`: Returns the Sum of All Values

Calculates the sum of numeric values in a column.

```sql
SELECT SUM(column_name) AS total_sum FROM table_name;

SELECT SUM(amount) FROM ecomcustomer;
```

## `AVG()`: Returns the Average Value

Calculates the average (mean) value of numeric values in a column.

```sql
SELECT AVG(column_name) AS average_value FROM table_name;

SELECT AVG(amount),2 FROM ecomcustomer;
```

## `MAX()`: Returns the Maximum Value

Returns the maximum value in a column or set of values.

```sql
SELECT MAX(column_name) AS max_value FROM table_name;

SELECT MAX(amount) FROM ecomcustomer;
```

## `MIN()`: Returns the Minimum Value

Returns the minimum value in a column or set of values.

```sql
SELECT MIN(column_name) AS min_value FROM table_name;

SELECT MIN(amount) FROM ecomcustomer;
```

## `ROUND()`: Rounds a Number to a Specified Number of Decimal Places

Rounds a numeric value to a specified number of decimal places.

```sql
SELECT ROUND(123.4567, 2) AS rounded_number;

SELECT ROUND(AVG(amount),2) FROM ecomcustomer;
```
