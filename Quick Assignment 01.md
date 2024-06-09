## Order of Execution in SQL

The typical order of execution for an SQL query is different from the order in which the statements are written. The correct logical order of execution is:

1. **FROM**: Specifies the table(s) from which to retrieve data.
2. **WHERE**: Filters rows based on specified conditions.
3. **GROUP BY**: Groups rows that have the same values in specified columns into summary rows.
4. **HAVING**: Filters groups based on specified conditions (similar to `WHERE`, but for groups).
5. **SELECT**: Specifies the columns to be returned by the query.
6. **ORDER BY**: Sorts the result set based on specified columns.
7. **LIMIT**: Specifies the maximum number of rows to return.

Here's a brief example to illustrate the order of execution:

```sql
SELECT city, COUNT(amount) AS counts
FROM ecomcustomer
WHERE amount > 100
GROUP BY city
HAVING COUNT(amount) >= 3
ORDER BY counts DESC
LIMIT 5;
```

### Explanation

1. **FROM ecomcustomer**: The query begins by retrieving data from the `ecomcustomer` table.
2. **WHERE amount > 100**: It then filters the rows to include only those where the `amount` is greater than 100.
3. **GROUP BY city**: The filtered rows are grouped by the `city` column.
4. **HAVING COUNT(amount) >= 3**: Groups are further filtered to include only those with a count of `amount` greater than or equal to 3.
5. **SELECT city, COUNT(amount) AS counts**: The specified columns (`city` and `counts`) are selected.
6. **ORDER BY counts DESC**: The result set is sorted by the `counts` column in descending order.
7. **LIMIT 5**: Finally, the query limits the result set to the top 5 rows.