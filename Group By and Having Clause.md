Certainly! Here's your input text formatted in Markdown:

### GROUP BY Statement

The `GROUP BY` statement groups rows that have the same values into summary rows. It is often used with aggregate functions (`COUNT()`, `MAX()`, `MIN()`, `SUM()`, `AVG()`) to group the result-set by one or more columns.

#### Syntax

```plsql
SELECT column_name(s), aggregate_function(column_name)
FROM table_name
GROUP BY column_name(s);
```

- **`column_name(s)`**: Specifies the column or columns that you want to group by.
- **`aggregate_function(column_name)`**: Applies an aggregate function (like `SUM()`, `COUNT()`, `MAX()`, `MIN()`, `AVG()`) to the grouped data.

#### Example

Consider the following example with a `payment` table:

```plsql
SELECT city, SUM(amount) AS Total
FROM ecomcustomer
GROUP BY city
ORDER BY total;
```

#### Explanation

- **`SELECT city, SUM(amount) AS total`**: Selects the `mode` column and calculates the sum of `amount` for each group defined by `city`. The result is aliased as `total`.
- **`FROM payment`**: Specifies the `payment` table from which data is selected.
- **`GROUP BY mode`**: Groups the rows based on the `city` column.

This query will produce a result set showing the total amount (`total`) for each distinct payment mode (`mode`) present in the `payment` table.

Adjust the table and column names (`payment`, `mode`, `amount`) based on your actual schema and data. This example demonstrates how to use `GROUP BY` to aggregate data and perform calculations across groups in SQL.

### HAVING Clause

The `HAVING` clause is used to apply a filter on the result of `GROUP BY` based on the specified condition. The `WHERE` clause places conditions on the selected columns, whereas the `HAVING` clause places conditions on groups created by the `GROUP BY` clause.

#### Syntax

```sql
SELECT column_name(s), aggregate_function(column_name)
FROM table_name
WHERE condition(s)
GROUP BY column_name(s)
HAVING condition(s)
ORDER BY column_name(s);
```

- **`column_name(s)`**: Specifies the column or columns that you want to group by.
- **`aggregate_function(column_name)`**: Applies an aggregate function (like `SUM()`, `COUNT()`, `MAX()`, `MIN()`, `AVG()`) to the grouped data.
- **`condition(s)`**: Specifies the conditions for filtering rows.

#### Example

Consider the following example with a `payment` table:

```sql
SELECT city, count(amount) AS counts
FROM ecomcustomer
GROUP BY city
HAVING count(amount)>=3
ORDER BY counts DESC;
```

#### Explanation

- **`SELECT city, count(amount) AS counts`**: Selects the `city` column and calculates the count of `amount` for each group defined by `city`. The result is aliased as `counts`.
- **`FROM ecomcustomer`**: Specifies the `ecomcustomer` table from which data is selected.
- **`GROUP BY city`**: Groups the rows based on the `city` column.
- **`HAVING count(amount) >= 3`**: Filters the groups to include only those with a count of `amount` greater than or equal to 3.
- **`ORDER BY counts DESC`**: Orders the result set by the `counts` column in descending order.

This query will produce a result set showing the count of `amount` (`total`) for each distinct payment mode (`mode`) present in the `payment` table, but only for those modes where the count is greater than or equal to 3. The result set is sorted in descending order based on the total count.