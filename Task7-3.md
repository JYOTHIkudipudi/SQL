# MySQL Table Modification Tasks

This document contains a complete SQL script that demonstrates how to perform various DDL operations on an **employees** table. The operations include:

- Adding new columns
- Modifying column data types
- Renaming columns
- Adding primary keys and unique constraints
- Setting default values
- Dropping columns and constraints
- Renaming the table

> **Note:** In a real-world scenario, you would only execute the operations you need. Some operations in this script are mutually exclusive (for example, dropping columns after renaming them) and are provided here for demonstration purposes.

---

## 1. Initial Table Definition

```sql
CREATE TABLE employees (
    emp_id INT,  
    emp_name VARCHAR(255), 
    salary FLOAT,        
    hire_date DATE,                            
    Location TEXT
);
```

---

## 2. Add New Columns

Add a new column "DOJ" (Date of Joining) and two new columns "phone_number" and "email".

```sql
ALTER TABLE employees 
    ADD COLUMN DOJ DATE,
    ADD COLUMN phone_number VARCHAR(20),
    ADD COLUMN email VARCHAR(50);
```

---

## 3. Modify Column Data Types

- Modify `salary` from `FLOAT` to `DECIMAL(10,2)`.
- Reduce the length of `emp_name` to 150 characters.

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2),
    MODIFY emp_name VARCHAR(150);
```

---

## 4. Rename Columns

- Rename `hire_date` to `joining_date`.
- Rename `Location` to `address`.

```sql
ALTER TABLE employees 
    CHANGE COLUMN hire_date joining_date DATE,
    CHANGE COLUMN Location address TEXT;
```

---

## 5. Add Primary Key and Set Auto Increment

Set `emp_id` as the primary key and modify it to be `AUTO_INCREMENT`.

```sql
ALTER TABLE employees 
    MODIFY emp_id INT AUTO_INCREMENT,
    ADD PRIMARY KEY (emp_id);
```

---

## 6. Add a Foreign Key

Assuming there is a `departments` table with a column `dept_id`, add a `dept_id` column to employees and set it as a foreign key.

```sql
ALTER TABLE employees 
    ADD COLUMN dept_id INT;

ALTER TABLE employees 
    ADD CONSTRAINT fk_department FOREIGN KEY (dept_id) REFERENCES departments(dept_id);
```

---

## 7. Add Unique Constraints

Add unique constraints to the `email` and `phone_number` columns.

```sql
ALTER TABLE employees 
    ADD CONSTRAINT unique_email UNIQUE (email),
    ADD CONSTRAINT unique_phone UNIQUE (phone_number);
```

---

## 8. Set Default Values

Set default values for columns:
- Default `salary` to `50000`.
- Default `joining_date` to `CURRENT_DATE`.

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2) DEFAULT 50000,
    MODIFY joining_date DATE DEFAULT CURRENT_DATE;
```

---

## 9. Drop Columns

Example commands to drop columns. (Ensure you refer to the current column names.)

- Drop the `address` column (which was renamed from `Location`).
- Drop the `email` and `phone_number` columns.

```sql
ALTER TABLE employees 
    DROP COLUMN address;

ALTER TABLE employees 
    DROP COLUMN email,
    DROP COLUMN phone_number;
```

---

## 10. Drop Constraints

Drop unique constraints and the primary key.

```sql
-- Drop unique constraints (MySQL implements these as indexes)
ALTER TABLE employees 
    DROP INDEX unique_email,
    DROP INDEX unique_phone;

-- Drop the primary key constraint
ALTER TABLE employees 
    DROP PRIMARY KEY;
```

---

## 11. Rename the Table

Rename the table from `employees` to `staff_members`. You can also rename multiple tables if needed.

```sql
-- Rename employees to staff_members
RENAME TABLE employees TO staff_members;

-- Example: Rename both employees and departments
-- RENAME TABLE employees TO staff_members, departments TO company_dept;
```
