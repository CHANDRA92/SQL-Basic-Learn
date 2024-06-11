# TIMESTAMP

The `TIMESTAMP` data type is used for values that contain both date and time parts.

- **TIME**: Contains only time, format `HH:MI:SS`
- **DATE**: Contains only date, format `YYYY-MM-DD`
- **YEAR**: Contains only year, format `YYYY` or `YY`
- **TIMESTAMP**: Contains date and time, format `YYYY-MM-DD HH:MI:SS`
- **TIMESTAMPTZ**: Contains date, time, and time zone

This formatting helps to distinguish between different types of date and time data in SQL databases.

## Functions/Operators

Below are the `TIMESTAMP` functions and operators in SQL, along with examples:

- **`SHOW TIMEZONE`**: Displays the current time zone setting.
  ```sql
  SHOW TIMEZONE;
  ```

- **`SELECT NOW()`**: Returns the current date and time.
  ```sql
  SELECT NOW();
  ```
  *Example Output*: `2024-06-09 12:34:56`

- **`SELECT TIMEOFDAY()`**: Returns the current date and time with more precision.
  ```sql
  SELECT TIMEOFDAY();
  ```
  *Example Output*: `Sun Jun  9 12:34:56.789012 2024`

- **`SELECT CURRENT_TIME`**: Returns the current time.
  ```sql
  SELECT CURRENT_TIME;
  ```
  *Example Output*: `12:34:56`

- **`SELECT CURRENT_DATE`**: Returns the current date.
  ```sql
  SELECT CURRENT_DATE;
  ```
  *Example Output*: `2024-06-09`
## EXTRACT Function

The `EXTRACT()` function extracts a part from a given date value.

#### Syntax

```sql
SELECT EXTRACT(part FROM date_field) FROM table_name;
```

#### Parts that can be extracted:

- **YEAR**
- **QUARTER**
- **MONTH**
- **WEEK**
- **DAY**
- **HOUR**
- **MINUTE**
- **DOW**: Day of the week
- **DOY**: Day of the year

#### Example

```plsql
SELECT EXTRACT (MONTH FROM order_date) AS order_month, order_date
FROM eComCustomer

SELECT EXTRACT (YEAR FROM order_date) AS order_month, order_date
FROM eComCustomer

SELECT EXTRACT (DOW FROM order_date) AS pay_day, order_date
FROM eComCustomer

SELECT EXTRACT (HOUR FROM order_date) AS pay_hour, order_date
FROM eComCustomer;

SELECT EXTRACT (QUARTER FROM order_date) AS pay_quarter, order_date
FROM eComCustomer;
```
