
# Note :-> [PostgreSQL String Functions Documentation](https://www.postgresql.org/docs/9.1/functions-string.html)

# Functions in SQL

Functions in SQL are database objects that contain a set of SQL statements to perform a specific task. A function typically accepts input parameters, performs actions based on these parameters, and then returns a result.

# Types of Functions

## 1. System Defined Functions

System-defined functions are built-in functions provided by the database management system (DBMS).

**Examples:**
- `RAND()`: Generates a random number.
- `ROUND()`: Rounds a numeric value.
- `UPPER()`: Converts a string to uppercase.
- `LOWER()`: Converts a string to lowercase.
- `COUNT()`: Returns the number of rows in a result set.
- `SUM()`: Calculates the sum of values.
- `MAX()`: Returns the maximum value in a set.
- `MIN()`: Returns the minimum value in a set.
- ...and many more.
### Commonly Used SQL Functions

Below are examples of commonly used SQL functions:

#### `RAND()`: Generates a Random Number

Generates a random number between 0 and 1.

```sql
SELECT RAND() AS random_number;
```

#### `ROUND()`: Rounds a Numeric Value

Rounds a numeric value to a specified number of decimal places (default is 0).

```sql
SELECT ROUND(123.4567, 2) AS rounded_number;
```

#### `UPPER()`: Converts a String to Uppercase

Converts all characters in a string to uppercase.

```sql
SELECT UPPER('hello') AS upper_case_string;
```

#### `LOWER()`: Converts a String to Lowercase

Converts all characters in a string to lowercase.

```sql
SELECT LOWER('Hello') AS lower_case_string;
```

#### `COUNT()`: Returns the Number of Rows in a Result Set

Counts the number of rows returned by a query.

```sql
SELECT COUNT(*) AS row_count FROM table_name;
```

#### `SUM()`: Calculates the Sum of Values

Calculates the sum of numeric values in a column.

```sql
SELECT SUM(column_name) AS total_sum FROM table_name;
```

#### `MAX()`: Returns the Maximum Value in a Set

Returns the maximum value in a column or set of values.

```sql
SELECT MAX(column_name) AS max_value FROM table_name;
```

#### `MIN()`: Returns the Minimum Value in a Set

Returns the minimum value in a column or set of values.

```sql
SELECT MIN(column_name) AS min_value FROM table_name;
```


## 2. User-Defined Functions

User-defined functions are functions that you can define yourself in SQL. Once defined, you can call them in SQL queries just like built-in functions.


### Most Used String Functions

String functions are used to perform operations on input strings and return an output string.

#### Converts the Value of a Field to Uppercase

```sql
UPPER(field_name)
```

Example:
```sql
SELECT UPPER('hello') AS upper_case_string;
```

#### Converts the Value of a Field to Lowercase

```sql
LOWER(field_name)
```

Example:
```sql
SELECT LOWER('Hello') AS lower_case_string;
```

#### Returns the Length of the Value in a Text Field

```sql
LENGTH(field_name)
```

Example:
```sql
SELECT LENGTH('example') AS string_length;
```

#### Extracts a Sub-string from a String

```sql
SUBSTRING(string_expression FROM start_position [FOR length])
```

Example:
```sql
SELECT SUBSTRING('name', 2, 3) AS extracted_string;
```

#### Returns the Current System Date and Time

```sql
NOW()
```

Example:
```sql
SELECT NOW() AS current_date_time;
```

#### Sets the Format of a Field

```sql
DATE_FORMAT(date_column, format_mask)
```

Example:
```sql
SELECT DATE_FORMAT(date_column, '%Y-%m-%d') AS formatted_date;
```

#### Concatenates Two or More Strings Together

```sql
CONCAT(string1, string2, ...)
```

Example:
```sql
SELECT CONCAT('Hello', ' ', 'World') AS concatenated_string;
```

#### Replaces All Occurrences of a Substring within a String with a New Substring

```sql
REPLACE(original_string, substring_to_replace, new_substring)
```

Example:
```sql
SELECT REPLACE('Hello, World', 'Hello', 'Hi') AS replaced_string;
```

#### Removes Leading and Trailing Spaces (or Other Specified Characters) from a String

```sql
TRIM([characters FROM] string)
```

Example:
```sql
SELECT TRIM('   hello   ') AS trimmed_string;
```


