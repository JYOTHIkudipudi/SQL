# SQL Employee Tasks

## EMPLOYEES TABLE

```sql
CREATE TABLE employee (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10,2),
    joining_date DATE,
    last_login TIMESTAMP,
    email VARCHAR(100)
);

INSERT INTO employee (name, department, salary, joining_date, last_login, email) VALUES
('John Doe', 'IT', 75000.50, '2020-03-15', '2024-03-10 08:30:00', 'john.doe@example.com'),
('Jane Smith', 'HR', 68000.00, '2019-07-22', '2024-03-11 09:15:00', 'jane.smith@example.com'),
('Michael Brown', 'Finance', 89000.75, '2018-10-10', '2024-03-12 10:45:00', 'michael.brown@example.com'),
('Emily Davis', 'Marketing', 72000.25, '2021-06-05', '2024-03-09 11:00:00', 'emily.davis@example.com'),
('David Wilson', 'IT', 95000.00, '2017-12-01', '2024-03-08 12:10:00', 'david.wilson@example.com'),
('Sophia Johnson', 'Sales', 78000.30, '2022-01-20', '2024-03-07 14:20:00', 'sophia.johnson@example.com'),
('Chris Martinez', 'Finance', 81000.00, '2019-05-30', '2024-03-06 09:50:00', 'chris.martinez@example.com'),
('Olivia Taylor', 'HR', 67000.45, '2020-08-15', '2024-03-05 10:10:00', 'olivia.taylor@example.com'),
('Daniel Anderson', 'IT', 88000.80, '2016-11-02', '2024-03-04 11:30:00', 'daniel.anderson@example.com'),
('Emma Thomas', 'Marketing', 73000.25, '2019-09-18', '2024-03-03 13:40:00', 'emma.thomas@example.com'),
('Ryan White', 'Sales', 77000.90, '2021-07-22', '2024-03-02 15:00:00', 'ryan.white@example.com'),
('Madison Lewis', 'Finance', 85000.60, '2018-06-25', '2024-03-01 08:25:00', 'madison.lewis@example.com'),
('William Scott', 'IT', 92000.30, '2017-04-14', '2024-02-29 09:45:00', 'william.scott@example.com'),
('Isabella Hall', 'HR', 69000.75, '2020-03-10', '2024-02-28 10:55:00', 'isabella.hall@example.com'),
('Ethan Allen', 'Marketing', 74000.10, '2019-01-05', '2024-02-27 11:35:00', 'ethan.allen@example.com'),
('Liam Young', 'Sales', 79500.50, '2022-02-18', '2024-02-26 13:20:00', 'liam.young@example.com'),
('Ava Hernandez', 'Finance', 86500.20, '2018-12-09', '2024-02-25 14:30:00', 'ava.hernandez@example.com'),
('James King', 'IT', 91000.75, '2017-05-20', '2024-02-24 15:50:00', 'james.king@example.com'),
('Charlotte Wright', 'HR', 70000.60, '2021-11-22', '2024-02-23 08:40:00', 'charlotte.wright@example.com'),
('Benjamin Lopez', 'Marketing', 76000.80, '2019-08-01', '2024-02-22 09:55:00', 'benjamin.lopez@example.com'),
('Alexander Hill', 'Sales', 78500.40, '2022-04-15', '2024-02-21 11:05:00', 'alexander.hill@example.com'),
('Mia Green', 'Finance', 87500.30, '2018-07-12', '2024-02-20 12:20:00', 'mia.green@example.com'),
('Lucas Adams', 'IT', 93000.10, '2016-09-30', '2024-02-19 13:45:00', 'lucas.adams@example.com'),
('Harper Nelson', 'HR', 71000.90, '2021-10-20', '2024-02-18 15:15:00', 'harper.nelson@example.com'),
('Henry Carter', 'Marketing', 75000.50, '2019-12-05', '2024-02-17 08:35:00', 'henry.carter@example.com'),
('Ella Mitchell', 'Sales', 79000.70, '2022-06-25', '2024-02-16 09:50:00', 'ella.mitchell@example.com'),
('Daniel Perez', 'Finance', 88000.40, '2018-05-11', '2024-02-15 10:20:00', 'daniel.perez@example.com'),
('Aria Roberts', 'IT', 94000.90, '2016-08-30', '2024-02-14 11:40:00', 'aria.roberts@example.com'),
('Matthew Evans', 'HR', 72000.30, '2021-09-15', '2024-02-13 13:10:00', 'matthew.evans@example.com'),
('Sofia Turner', 'Marketing', 77000.60, '2019-11-10', '2024-02-12 14:25:00', 'sofia.turner@example.com');
```

## STRING FUNCTIONS TASKS:

1. **Retrieve all employee names in uppercase:**
    ```sql
    SELECT UPPER(name) FROM employee;
    ```

2. **Extract only the domain name from the employee email addresses:**
    ```sql
    SELECT SUBSTRING_INDEX(email, '@', -1) AS domain FROM employee;
    ```

3. **Find the length of each employee's name:**
    ```sql
    SELECT name, CHAR_LENGTH(name) AS name_length FROM employee;
    ```

4. **Display the employee name along with their department in a single output:**
    ```sql
    SELECT CONCAT(name, ' - ', department) AS employee_detail FROM employee;
    ```

5. **Retrieve the first five characters from each employee's email:**
    ```sql
    SELECT LEFT(email, 5) FROM employee;
    ```

6. **Replace 'IT' with 'Information Technology' in the department column:**
    ```sql
    SELECT REPLACE(department, 'IT', 'Information Technology') AS updated_department FROM employee;
    ```

7. **Remove leading and trailing spaces from employee names:**
    ```sql
    SELECT TRIM(name) FROM employee;
    ```

8. **Get the first three characters of each employee's name:**
    ```sql
    SELECT LEFT(name, 3) FROM employee;
    ```

9. **Get the last ten characters of each employee's email:**
    ```sql
    SELECT RIGHT(email, 10) FROM employee;
    ```

10. **Locate the first occurrence of 'a' in each employee's name:**
    ```sql
    SELECT name, INSTR(name, 'a') AS a_position FROM employee;
    ```

11. **Reverse the characters in employee names:**
    ```sql
    SELECT REVERSE(name) FROM employee;
    ```

12. **Pad employee names with '*' to a total width of 20 characters:**
    ```sql
    SELECT LPAD(name, 20, '*') FROM employee;
    ```

13. **Pad department names with '-' to a total width of 15 characters:**
    ```sql
    SELECT RPAD(department, 15, '-') FROM employee;
    ```

14. **Find the number of characters in each email:**
    ```sql
    SELECT email, CHAR_LENGTH(email) AS email_length FROM employee;
    ```

15. **Identify the position of '@' in each email:**
    ```sql
    SELECT email, INSTR(email, '@') AS at_position FROM employee;
    ```

16. **Insert 'XYZ' at the third character of each employee's name:**
    ```sql
    SELECT CONCAT(LEFT(name, 2), 'XYZ', SUBSTRING(name, 3)) AS modified_name FROM employee;
    ```

17. **Get the ASCII value of the first character of each name:**
    ```sql
    SELECT name, ASCII(LEFT(name, 1)) AS ascii_value FROM employee;
    ```

18. **Check the department position in a predefined list ('IT', 'HR', 'Finance', 'Marketing', 'Sales'):**
    ```sql
    SELECT department, FIND_IN_SET(department, 'IT,HR,Finance,Marketing,Sales') AS position FROM employee;
    ```

19. **Retrieve the second item ('Finance') from a predefined list:**
    ```sql
    SELECT SUBSTRING_INDEX(SUBSTRING_INDEX('IT,HR,Finance,Marketing,Sales', ',', 2), ',', -1) AS second_item;
    ```

20. **Create a set from predefined department values and retrieve a combination based on an index:**
    ```sql
    SELECT ELT(3, 'IT', 'HR', 'Finance', 'Marketing', 'Sales') AS third_item;
    ```

## NUMERIC FUNCTIONS TASKS:

1. **Increase each employee's salary by 10% and display the new salary:**
    ```sql
    SELECT name, salary, salary * 1.10 AS new_salary FROM employee;
    ```

2. **Deduct a tax of 5% from each employee's salary and show the amount after tax deduction:**
    ```sql
    SELECT name, salary, salary * 0.95 AS after_tax_salary FROM employee;
    ```

3. **Show the absolute difference between each employee's salary and 80000:**
    ```sql
    SELECT name, salary, ABS(salary - 80000) AS abs_difference FROM employee;
    ```

4. **Display each employee's salary rounded to the nearest thousand:**
    ```sql
    SELECT name, salary, ROUND(salary, -3) AS rounded_salary FROM employee;
    ```

5. **Show the salary of each employee truncated to remove decimal values:**
    ```sql
    SELECT name, salary, TRUNCATE(salary, 0) AS truncated_salary FROM employee;
    ```

6. **Convert each employee's salary into an integer value:**
    ```sql
    SELECT name, salary, CAST(salary AS SIGNED) AS int_salary FROM employee;
    ```

7. **Show the ceiling (next highest integer) value of each employee's salary:**
    ```sql
    SELECT name, salary, CEIL(salary) AS ceiling_salary FROM employee;
    ```

8. **Show the floor (next lowest integer) value of each employee's salary:**
    ```sql
    SELECT name, salary, FLOOR(salary) AS floor_salary FROM employee;
    ```

9. **Display the last 3 digits of each employee's salary:**
    ```sql
    SELECT name, salary, RIGHT(CAST(salary AS CHAR), 3) AS last_three_digits FROM employee;
    ```

10. **Show the square of each employee's salary:**
    ```sql
    SELECT name, salary, POW(salary, 2) AS salary_squared FROM employee;
    ```

11. **Show the square root of each employee's salary:**
    ```sql
    SELECT name, salary, SQRT(salary) AS salary_sqrt FROM employee;
    ```

12. **Display a random number between 1 and 100 for each employee:**
    ```sql
    SELECT name, FLOOR(1 + (RAND() * 100)) AS random_number FROM employee;
    ```

13. **Show whether each employee's salary is even or odd:**
    ```sql
    SELECT name, salary, IF(MOD(salary, 2) = 0, 'Even', 'Odd') AS even_or_odd FROM employee;
    ```

14. **Show the power of each employee's salary raised to 3:**
    ```sql
    SELECT name, salary, POW(salary, 3) AS salary_cubed FROM employee;
    ```

15. **Convert each employee's salary into a string and concatenate "USD" at the end:**
    ```sql
    SELECT name, salary, CONCAT(CAST(salary AS CHAR), ' USD') AS salary_usd FROM employee;
    ```

16. **Convert the salary into a string and extract only the first 5 characters:**
    ```sql
    SELECT name, salary, LEFT(CAST(salary AS CHAR), 5) AS first_five_chars FROM employee;
    ```
