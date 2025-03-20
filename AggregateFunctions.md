# Aggregate Functions

Aggregate functions perform operations on multiple values (columns) and print the result as a summarized value.

1. **COUNT()**: Retrieves the number of records in a database.
    - Using in two formats:
        ```sql
        SELECT COUNT(*) FROM table_name; -- Counts null values too
        SELECT COUNT(col_name) FROM table_name; -- Doesn't count null values
        ```

2. **SUM()**: Adds all the values present in the column.
    ```sql
    SELECT SUM(salary) FROM employees;
    ```

3. **AVG()**: Computes the average of a set of values.
    ```sql
    SELECT AVG(salary) FROM employees;
    ```

4. **MIN()**: Returns the minimum value.
    ```sql
    SELECT MIN(salary) FROM employees;
    ```

5. **MAX()**: Returns the maximum value.
    ```sql
    SELECT MAX(salary) FROM employees;
    ```

    # Aggregate Functions Tasks

## Table Creation and Data Insertion

```sql
CREATE TABLE sales_data (
    id INT PRIMARY KEY,
    salesperson VARCHAR(100),
    region VARCHAR(50),
    total_sales DECIMAL(10,2),
    commission DECIMAL(10,2),
    sales_date DATE,
    num_products_sold INT
);

INSERT INTO sales_data (id, salesperson, region, total_sales, commission, sales_date, num_products_sold) VALUES
(1, 'Alice Johnson', 'North', 15000.50, 1500.50, '2024-03-01', 120),
(2, 'Bob Smith', 'South', 18000.75, 1800.75, '2024-03-02', 140),
(3, 'Charlie Brown', 'East', 22000.00, 2200.00, '2024-03-03', 160),
(4, 'David Wilson', 'West', 19500.25, 1950.25, '2024-03-04', 130),
(5, 'Eve Adams', 'North', 25000.60, 2500.60, '2024-03-05', 170),
(6, 'Frank White', 'South', 17000.85, 1700.85, '2024-03-06', 110),
(7, 'Grace Lee', 'East', 21000.90, 2100.90, '2024-03-07', 155),
(8, 'Henry Ford', 'West', 16000.40, 1600.40, '2024-03-08', 125),
(9, 'Isabel Green', 'North', 20000.95, 2000.95, '2024-03-09', 150),
(10, 'Jack Black', 'South', 23000.30, 2300.30, '2024-03-10', 165);
```

## Tasks and Answers

1. **Find the total sales amount across all regions**:
   ```sql
   SELECT SUM(total_sales) AS total_sales_amount FROM sales_data;
   ```

2. **Find the total commission paid**:
   ```sql
   SELECT SUM(commission) AS total_commission_paid FROM sales_data;
   ```

3. **Find the average total sales per salesperson**:
   ```sql
   SELECT AVG(total_sales) AS average_total_sales_per_salesperson FROM sales_data;
   ```

4. **Find the average number of products sold per salesperson**:
   ```sql
   SELECT AVG(num_products_sold) AS average_products_sold_per_salesperson FROM sales_data;
   ```

5. **Count the total number of sales transactions**:
   ```sql
   SELECT COUNT(*) AS total_sales_transactions FROM sales_data;
   ```

6. **Count how many sales were made in the North region**:
   ```sql
   SELECT COUNT(*) AS sales_in_north_region FROM sales_data WHERE region = 'North';
   ```

7. **Find the minimum total sales recorded**:
   ```sql
   SELECT MIN(total_sales) AS minimum_total_sales FROM sales_data;
   ```

8. **Find the lowest commission paid**:
   ```sql
   SELECT MIN(commission) AS lowest_commission_paid FROM sales_data;
   ```

9. **Find the highest total sales recorded**:
   ```sql
   SELECT MAX(total_sales) AS highest_total_sales FROM sales_data;
   ```

10. **Find the maximum number of products sold by a salesperson**:
    ```sql
    SELECT MAX(num_products_sold) AS maximum_products_sold FROM sales_data;
    ```
