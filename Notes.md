# Introduction to SQL

## Database
A database is a collection of data.

## DBMS
DBMS (Database Management System) is a software application that interacts with the database.

### Consider a Scenario:
If a user wants to interact with the database, they can't directly interact with it. Instead, they use a software application to interact with the database, and that software application uses a programming language, which is SQL.
```
user -> software application -> database
```

## Types of Databases
There are 2 types of databases:
1. **Relational Database**: Stores data in the form of tables.
   - Examples: MySQL, Oracle
2. **Non-Relational Database**: Does not store data in the form of tables, but in key-value pairs.
   - Example: MongoDB

## SQL (Structured Query Language)
SQL is a programming language that interacts with the database.

### Datatypes in SQL
1. **Numeric**: int, float, decimal(precision, scale)
2. **Character**: char(size), varchar(size)
3. **Date**: yyyy-mm-dd

### SQL Commands
There are 5 types of SQL commands:
1. **DQL (Data Query Language)**
   - Command: SELECT
2. **DML (Data Manipulation Language)**
   - Commands: INSERT, UPDATE, DELETE
3. **DDL (Data Definition Language)**
   - Commands: CREATE, ALTER, RENAME, DROP, TRUNCATE
4. **DCL (Data Control Language)**
   - Commands: GRANT, REVOKE
5. **TCL (Transaction Control Language)**
   - Commands: COMMIT, ROLLBACK, SAVEPOINT

## SQL Syntax

### Create a Table
```sql
CREATE TABLE table_name (
    col_name data_type,
    col_name data_type,
    ...
);
```

### Insert Data
```sql
INSERT INTO table_name VALUES (value1, value2, ...), (value1, value2, ...);

-- or

INSERT INTO table_name (col1, col2, col3, ...) VALUES (value1, value2, ...);
```

### Truncate Table
```sql
TRUNCATE TABLE table_name;
```

### Drop Table
```sql
DROP TABLE table_name;
```

## Constraints in SQL
Constraints are rules applied to columns in a table:
1. **NOT NULL**: Does not allow null values.
2. **UNIQUE**: Accepts only unique values, no duplicates.
3. **DEFAULT**: Adds a default value if none is specified.
4. **CHECK**: Checks a condition before inserting data.
5. **PRIMARY KEY**: Combination of NOT NULL and UNIQUE.
6. **FOREIGN KEY**: Builds a relationship between two tables.

### ALTER Command
Used to modify the structure of a table.
- **ADD**:
    ```sql
    ALTER TABLE table_name ADD new_col_name datatype;
    ```
- **DROP**:
    ```sql
    ALTER TABLE table_name DROP column_name;
    ALTER TABLE table_name DROP col_name1, col_name2;
    ```
- **MODIFY**:
    ```sql
    ALTER TABLE table_name MODIFY column_name datatype;
    ```
- **RENAME**:
    ```sql
    ALTER TABLE table_name RENAME COLUMN old_col_name TO new_col_name;
    ```

## Operators in SQL
- **Arithmetic Operators**: `+`, `-`, `*`, `/`, `%`
- **Relational Operators**: `<`, `>`, `<=`, `>=`, `!=`, `<>`
- **Logical Operators**: `AND`, `OR`, `NOT`

## Clauses in SQL
- **WHERE Clause**: Used to filter records.
    ```sql
    SELECT * FROM table_name WHERE condition;
    ```

## Update Command
Used to modify existing data in the table.
```sql
UPDATE table_name SET col_name='value1', col_name='value2', ... WHERE condition;
```

## Delete Command
```sql
DELETE FROM table_name WHERE condition;
```

## Functions in SQL

### Scalar Functions
1. **Numeric Functions**:
    - `ABS()`: Returns the absolute value of a number.
        ```sql
        SELECT ABS(number);
        ```
    - `CEIL()`: Returns the greatest integer value nearest to the given number.
        ```sql
        SELECT CEIL(4.567); -- Returns 5
        ```
    - `FLOOR()`: Returns the smallest integer value nearest to the given number.
        ```sql
        SELECT FLOOR(3.890); -- Returns 3
        ```
    - `DIV`: Calculates integer division.
        ```sql
        SELECT 10 DIV 5; -- Returns 2
        ```
    - `MOD()`: Returns the remainder of a division.
        ```sql
        SELECT MOD(25, 2); -- Returns 1
        ```
    - `POW(base, exponent)`: Returns the value of base raised to the power of exponent.
        ```sql
        SELECT POW(2, 3); -- Returns 8
        ```
    - `SQRT()`: Returns the square root of a number.
        ```sql
        SELECT SQRT(165);
        ```
    - `ROUND(number, d)`: Rounds a number to the specified number of digits.
        ```sql
        SELECT ROUND(4.5678, 2); -- Returns 4.57
        ```
    - `TRUNCATE(number, d)`: Truncates a number to the specified number of decimal places.
        ```sql
        SELECT TRUNCATE(9.07856689, 3); -- Returns 9.078
        ```

2. **String Functions**:
    - `ASCII()`: Returns the ASCII value of a character.
        ```sql
        SELECT ASCII('A'); -- Returns 65
        ```
    - `CHAR_LENGTH()`: Returns the length of a string.
        ```sql
        SELECT CHAR_LENGTH('TECHNICAL HUB'); -- Returns 13
        ```
    - `LOWER()`, `UPPER()`: Converts a string to lower or upper case.
    - `REVERSE()`: Reverses a string.
        ```sql
        SELECT REVERSE('SQL'); -- Returns 'LQS'
        ```
    - `CONCAT()`: Concatenates two or more strings.
        ```sql
        SELECT CONCAT('Hello', ' ', 'World'); -- Returns 'Hello World'
        ```
    - `INSTR()`: Returns the position of the first occurrence of a substring.
        ```sql
        SELECT INSTR('Hello World', 'World'); -- Returns 7
        ```
    - `SUBSTR()`: Returns a substring starting from a specified position.
        ```sql
        SELECT SUBSTR('Welcome World', 2, 8); -- Returns 'elcome W'
        ```
    - `LEFT()`, `RIGHT()`: Extracts a specified number of characters from the left or right side of a string.
    - `REPLACE()`: Replaces occurrences of a substring within a string.
        ```sql
        SELECT REPLACE('Hello World', 'World', 'SQL'); -- Returns 'Hello SQL'
        ```
    - `STRCMP()`: Compares two strings.
        - Returns 0 if they are equal.
        - Returns -1 if string1 < string2.
        - Returns 1 if string1 > string2.
    - `LPAD()`, `RPAD()`: Pads a string to a specified length.
    - `TRIM()`: Removes leading and trailing spaces from a string.

3. **Date & Time Functions**:
    - `CURDATE()`, `CURRENT_DATE`: Returns the current date.
    - `CURTIME()`, `CURRENT_TIME`: Returns the current time.
    - `CURRENT_TIMESTAMP()`, `NOW()`, `SYSDATE()`: Returns the current date and time.
    - `DATE_ADD(date, INTERVAL value addunit)`: Adds an interval to a date.
    - `YEAR(date)`: Extracts the year from a date.
    - `HOUR(time)`: Extracts the hour from a time.
    - `ADDTIME(time1, time2)`: Adds two time values.
    - `DATE_FORMAT(date, format)`, `TIME_FORMAT(time, format)`: Formats a date or time value.

### Aggregate Functions
1. **COUNT()**: Returns the number of records.
    ```sql
    SELECT COUNT(*) FROM table_name;
    SELECT COUNT(column_name) FROM table_name;
    ```
2. **SUM()**: Returns the sum of values.
    ```sql
    SELECT SUM(column_name) FROM table_name;
    ```
3. **AVG()**: Returns the average of values.
    ```sql
    SELECT AVG(column_name) FROM table_name;
    ```
4. **MIN()**: Returns the minimum value.
    ```sql
    SELECT MIN(column_name) FROM table_name;
    ```
5. **MAX()**: Returns the maximum value.
    ```sql
    SELECT MAX(column_name) FROM table_name;
    ```
