# Functions in SQL

## Reusability and Modularity

Functions in SQL provide reusability and modularity. They can be used to compute mathematical calculations, modify text data, and handle date and time values.

## Types of Functions

There are two types of functions in SQL:
1. **Scalar Functions**
2. **Aggregate Functions**

### Scalar Functions

Scalar functions perform operations on individual data elements and return a single value as a result.

#### Numeric Functions

Numeric functions perform operations on numerical data types.

- **ABS()**: Returns the absolute value of a number.
  - **Syntax**: `SELECT ABS(number);`
  - **Example**: `SELECT ABS(-4.7890);`

- **CEIL()**: Returns the smallest integer value greater than or equal to the given number.
  - **Example**: `SELECT CEIL(4.567);`   // Result: 5

- **FLOOR()**: Returns the largest integer value less than or equal to the given number.
  - **Example**: `SELECT FLOOR(3.890);`  // Result: 3

- **DIV()**: Performs integer division and returns the integer quotient.
  - **Syntax**: `x DIV y` or `SELECT x / y;`
  - **Example**: `SELECT 10 DIV 5;` or `SELECT 10 / 5;` // Result: 2

- **MOD()**: Returns the remainder of the division of two numbers.
  - **Syntax**: `SELECT MOD(x, y);`
  - **Example**: `SELECT MOD(10, 3);` // Result: 1

- **POW()**: Returns the value of a number raised to the power of another number.
  - **Syntax**: `SELECT POW(base, exponent);`
  - **Example**: `SELECT POW(2, 3);` // Result: 8

- **SQRT()**: Returns the square root of a number.
  - **Syntax**: `SELECT SQRT(number);`
  - **Example**: `SELECT SQRT(169);` // Result: 13

- **ROUND()**: Rounds a number to a specified number of decimal places.
  - **Syntax**: `SELECT ROUND(number, d);`
  - **Examples**: 
    - `SELECT ROUND(4.5678, 2);` // Result: 4.57
    - `SELECT ROUND(4.65432, 2);` // Result: 4.65

- **TRUNCATE()**: Truncates a number to a specified number of decimal places.
  - **Syntax**: `SELECT TRUNCATE(number, d);`
  - **Example**: `SELECT TRUNCATE(9.07856689, 3);` // Result: 9.078

#### String Functions

String functions are used to modify or manipulate text data.

- **ASCII()**: Returns the ASCII value of a given character.
  - **Example**: `SELECT ASCII('A');` // Result: 65

- **CHAR_LENGTH()** or **CHARACTER_LENGTH()**: Returns the length of a string in characters.
  - **Syntax**: `SELECT CHAR_LENGTH('string');`
  - **Example**: `SELECT CHAR_LENGTH('TECHNICAL HUB');` // Result: 13

- **LENGTH()**: Returns the length of a string in bytes.
  - **Syntax**: `SELECT LENGTH('string');`
  - **Example**: `SELECT LENGTH('THUB');` // Result: 4

- **LOWER()** or **LOWERCASE()**: Converts a string to lowercase.
  - **Example**: `SELECT LOWER('THUB');` // Result: thub

- **UPPER()**: Converts a string to uppercase.
  - **Example**: `SELECT UPPER('thub');` // Result: THUB

- **REVERSE()**: Reverses the characters in a string.
  - **Example**: `SELECT REVERSE('THUB');` // Result: BUHT

- **CONCAT()**: Concatenates two or more strings into one string.
  - **Syntax**: `SELECT CONCAT(string1, string2, ...);`
  - **Example**: `SELECT first_name, last_name, CONCAT(first_name, ' ', last_name) FROM students;`

- **CONCAT_WS()**: Concatenates strings with a separator.
  - **Syntax**: `SELECT CONCAT_WS(separator, string1, string2, ...);`

- **INSTR()**: Returns the position of the first occurrence of a substring within a string.
  - **Syntax**: `SELECT INSTR(string, substring);`
  - **Example**: `SELECT INSTR('HELLO WORLD HI', 'HI');` // Result: 12

- **SUBSTR()**: Returns a substring starting from a specified position.
  - **Syntax**: `SELECT SUBSTR(string, start, length);`
  - **Example**: `SELECT SUBSTR('WELCOME WORLD', 2, 8);` // Result: ELCOME W

- **LEFT()**: Extracts a specified number of characters from the left side of a string.
  - **Syntax**: `SELECT LEFT(string, number_of_chars);`
  - **Example**: `SELECT LEFT('JYOTHI', 5);` // Result: JYOTH

- **RIGHT()**: Extracts a specified number of characters from the right side of a string.
  - **Syntax**: `SELECT RIGHT(string, number_of_chars);`
  - **Example**: `SELECT RIGHT('AMMA', 2);` // Result: MA

- **REPLACE()**: Replaces occurrences of a substring within a string with a new substring.
  - **Syntax**: `SELECT REPLACE(string, substring, new_string);`
  - **Example**: `SELECT REPLACE('HiHELLOworld', 'HELLO', 'Programming');` // Result: HiProgrammingworld

- **STRCMP()**: Compares two strings.
  - **Syntax**: `SELECT STRCMP(string1, string2);`
  - **Results**:
    - 0 if both strings are equal
    - -1 if string1 < string2
    - 1 if string1 > string2
  - **Example**: `SELECT STRCMP('VIRAT', 'KOHLI');`

- **LPAD()**: Pads a string on the left side with a specified character to a specified length.
  - **Syntax**: `SELECT LPAD(string, fixed_length, pad_string);`
  - **Example**: `SELECT LPAD('ABC', 10, '*');` // Result: *******ABC

- **RPAD()**: Pads a string on the right side with a specified character to a specified length.
  - **Syntax**: `SELECT RPAD(string, fixed_length, pad_string);`
  - **Example**: `SELECT RPAD('ABC', 10, '*');` // Result: ABC*******

- **TRIM()**: Removes leading and trailing spaces from a string.
  - **Syntax**: `SELECT TRIM(string);`
  - **Example**: `SELECT TRIM('    HELLO   ');` // Result: HELLO

- **LTRIM()**: Removes leading spaces from a string.
  - **Syntax**: `SELECT LTRIM(string);`
  - **Example**: `SELECT LTRIM('    HELLO   ');` // Result: HELLO

- **RTRIM()**: Removes trailing spaces from a string.
  - **Syntax**: `SELECT RTRIM(string);`
  - **Example**: `SELECT RTRIM('    HELLO   ');` // Result: HELLO

### Date & Time Functions

Date and time functions are used to manipulate and handle date and time values.

### Aggregate Functions

Aggregate functions perform operations on multiple values (a column) and return a summarized result.
