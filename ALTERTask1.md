
# Employees Table Tasks

This document outlines various SQL DDL operations performed on an **Employees** table. The operations include:

- Creating the initial table
- Adding new columns
- Dropping columns
- Modifying column data types
- Renaming columns
- Renaming tables
- Adding a primary key
- Adding unique constraints
- Dropping constraints
- Setting default values

> **Note:** Some tasks may conflict when applied sequentially on the same table. In a real scenario, you would only execute the required operations. This file is for demonstration purposes.

---

## 1. Create the Initial Employees Table

Create a table with the following columns:
- `emp_id`
- `emp_name`
- `salary`
- `hire_date`
- `location`

```sql
CREATE TABLE employees (
    emp_id INT,
    emp_name VARCHAR(255),
    salary FLOAT,
    hire_date DATE,
    location TEXT
);
```

---

## 2. Add New Columns

### 2.1. Add a new column "DOJ"
### 2.2. Add two new columns "Phone_Number" and "email"

```sql
ALTER TABLE employees 
    ADD COLUMN DOJ DATE,
    ADD COLUMN phone_number VARCHAR(20),
    ADD COLUMN email VARCHAR(50);
```

---

## 3. Drop Columns

### 3.1. Drop the column "location"
### 3.2. Drop two columns "email" and "phone_number"

```sql
-- Drop the "location" column (note: if this is dropped, you cannot later rename it to "address")
ALTER TABLE employees 
    DROP COLUMN location;

-- Alternatively, if you want to drop "email" and "phone_number" later:
ALTER TABLE employees 
    DROP COLUMN email,
    DROP COLUMN phone_number;
```

---

## 4. Modify Column Data Types

### 4.1. Modify `salary` from FLOAT to DECIMAL(10,2)
### 4.2. Reduce `emp_name` length to 150 characters

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2),
    MODIFY emp_name VARCHAR(150);
```

---

## 5. Rename Columns

### 5.1. Rename `hire_date` to `joining_date`
### 5.2. Rename `location` to `address`

> **Note:** If you already dropped the `location` column in Task 3, you cannot rename it. For demonstration, assume this step is applied before dropping `location`.

```sql
ALTER TABLE employees 
    CHANGE COLUMN hire_date joining_date DATE,
    CHANGE COLUMN location address TEXT;
```

---

## 6. Rename the Table

### 6.1. Rename **employees** to **staff_members**
### 6.2. Rename **employees** to **staff_members** and **departments** to **company_dept**

```sql
-- Rename employees to staff_members:
RENAME TABLE employees TO staff_members;

-- Example: Renaming both tables in one command:
-- RENAME TABLE employees TO staff_members, departments TO company_dept;
```

---

## 7. Add a Primary Key

### 7.1. Set `emp_id` as the Primary Key

```sql
ALTER TABLE employees 
    ADD PRIMARY KEY (emp_id);
```

*Optionally, you may want to modify `emp_id` to be AUTO_INCREMENT:*

```sql
ALTER TABLE employees 
    MODIFY emp_id INT AUTO_INCREMENT;
```

---

## 8. Add Unique Constraints

### 8.1. Add a unique constraint to the `email` column
### 8.2. Add a unique constraint to the `phone_number` column

```sql
ALTER TABLE employees 
    ADD CONSTRAINT unique_email UNIQUE (email),
    ADD CONSTRAINT unique_phone UNIQUE (phone_number);
```

---

## 9. Drop Constraints

### 9.1. Drop the unique constraint on `email`
### 9.2. Drop the unique constraint on `phone_number`
### 9.3. Drop the Primary Key Constraint

```sql
-- Drop unique constraints (they are implemented as indexes in MySQL)
ALTER TABLE employees 
    DROP INDEX unique_email,
    DROP INDEX unique_phone;

-- Drop the primary key:
ALTER TABLE employees 
    DROP PRIMARY KEY;
```

> **Note:** If `emp_id` is set as AUTO_INCREMENT, you might need to modify the column before dropping the primary key.

---

## 10. Set Default Values for Columns

### 10.1. Set default value of `salary` to 50000
*(Using the DECIMAL(10,2) data type from Task 4)*

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2) DEFAULT 50000;
```
