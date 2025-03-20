# Date & Time Functions

Date & Time functions are used when you are generating reports or if you want to schedule reminders to do tasks.

1. **CURDATE()** or **CURRENT_DATE**: Returns the current date.
    ```sql
    SELECT CURRENT_DATE();
    ```

2. **CURTIME()** or **CURRENT_TIME**: Returns the current time.
    ```sql
    SELECT CURTIME();
    ```

3. If we want both time and date values, we can use **CURRENT_TIMESTAMP**, **NOW()**, or **SYSDATE()**.
    ```sql
    SELECT CURRENT_TIMESTAMP();
    SELECT NOW();
    SELECT SYSDATE();
    ```

4. **DATE_ADD()**: Adds an interval to a date. For example, to add 30 days to the current date:
    ```sql
    SELECT DATE_ADD(CURDATE(), INTERVAL 30 DAY);
    ```

5. **DATE_SUB()**: Subtracts an interval from a date. For example, to subtract 2 years from the current date:
    ```sql
    SELECT DATE_SUB(CURDATE(), INTERVAL 2 YEAR);
    ```

6. **YEAR(date)**: Extracts the year from a date.
    ```sql
    SELECT YEAR(CURDATE());
    ```

7. **HOUR(time)**: Extracts the hour from a time.

8. **ADDTIME()**: Takes two parameters: time1 value and time2 value.

9. **DATE_FORMAT()**: Formats a date value according to a specified format.
    ```sql
    SELECT DATE_FORMAT(CURDATE(), '%d %m %y');
    SELECT CURDATE();
    ```

10. **TIME_FORMAT(time, format)**: Formats a time value according to a specified format.
    ```sql
    SELECT TIME_FORMAT('23:45:32', '%r'); -- Returns '11:45:32 PM'
    ```
    - If we want to display in 24-hour format: `%H`
    - If we want to display in 12-hour format: `%h`
    - Display minutes: `%i`
    - Display seconds: `%s`
    - Display AM or PM: `%p`
    - Display in 12-hour format with AM or PM: `%r`
    - Display in 24-hour format: `%T`



# Date & Time Functions Tasks

## Table Creation and Data Insertion

```sql
CREATE TABLE date_time_data (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    order_date DATETIME,
    delivery_date DATE,
    login_time TIME,
    birth_date DATE,
    event_timestamp TIMESTAMP
);

INSERT INTO date_time_data (id, name, order_date, delivery_date, login_time, birth_date, event_timestamp) VALUES
(1, 'Alice Johnson', '2024-03-01 14:30:00', '2024-03-05', '14:15:30', '1990-05-15', '2024-03-10 12:00:00'),
(2, 'Bob Smith', '2024-02-15 09:45:00', '2024-02-20', '09:30:00', '1985-08-25', '2024-02-18 16:30:45'),
(3, 'Charlie Brown', '2024-01-10 18:20:00', '2024-01-15', '18:10:15', '1992-11-05', '2024-01-12 08:45:30'),
(4, 'David Wilson', '2024-04-05 12:10:00', '2024-04-10', '12:05:10', '1987-07-30', '2024-04-07 14:20:15'),
(5, 'Eve Adams', '2024-05-20 08:15:00', '2024-05-25', '08:10:05', '1995-09-12', '2024-05-22 10:50:20'),
(6, 'Frank White', '2024-06-12 20:30:00', '2024-06-17', '20:25:40', '1993-03-18', '2024-06-15 18:10:55'),
(7, 'Grace Lee', '2024-07-01 10:05:00', '2024-07-06', '10:00:00', '1989-12-22', '2024-07-03 09:55:35'),
(8, 'Henry Ford', '2024-08-15 22:45:00', '2024-08-20', '22:30:25', '1980-06-07', '2024-08-18 21:40:10'),
(9, 'Isabel Green', '2024-09-05 16:20:00', '2024-09-10', '16:10:45', '1998-02-14', '2024-09-07 17:55:00'),
(10, 'Jack Black', '2024-10-10 11:55:00', '2024-10-15', '11:50:30', '1991-04-08', '2024-10-12 13:45:25');
```

## Tasks and Answers

1. **Retrieve the current date, current time & current timestamp**:
   ```sql
   SELECT CURRENT_DATE() AS current_date;
   SELECT CURRENT_TIME() AS current_time;
   SELECT CURRENT_TIMESTAMP() AS current_timestamp;
   ```

2. **Get the timestamp for the current moment**:
   ```sql
   SELECT NOW() AS current_moment;
   ```

3. **Extract the year and month from order_date**:
   ```sql
   SELECT id, name, YEAR(order_date) AS order_year, MONTH(order_date) AS order_month FROM date_time_data;
   ```

4. **Get only the hour and minute from login_time**:
   ```sql
   SELECT id, name, HOUR(login_time) AS login_hour, MINUTE(login_time) AS login_minute FROM date_time_data;
   ```

5. **Calculate the number of days between order_date and delivery_date**:
   ```sql
   SELECT id, name, DATEDIFF(delivery_date, order_date) AS days_between FROM date_time_data;
   ```

6. **Find out the date 30 days after the order_date**:
   ```sql
   SELECT id, name, DATE_ADD(order_date, INTERVAL 30 DAY) AS date_after_30_days FROM date_time_data;
   ```

7. **Display order_date in a readable format using format options**:
   ```sql
   SELECT id, name, DATE_FORMAT(order_date, '%W, %M %d, %Y %h:%i %p') AS formatted_order_date FROM date_time_data;
   ```

8. **Convert event_timestamp to a custom format**:
   ```sql
   SELECT id, name, DATE_FORMAT(event_timestamp, '%d-%m-%Y %H:%i:%s') AS custom_event_timestamp FROM date_time_data;
   ```

9. **Find the age of each person**:
   ```sql
   SELECT id, name, TIMESTAMPDIFF(YEAR, birth_date, CURDATE()) AS age FROM date_time_data;
   ```

10. **Find how many seconds have passed since each event_timestamp**:
    ```sql
    SELECT id, name, TIMESTAMPDIFF(SECOND, event_timestamp, NOW()) AS seconds_since_event FROM date_time_data;
