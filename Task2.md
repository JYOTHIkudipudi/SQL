

## 1. Initial Table Definitions

### 1.1. Employees Table

```sql
CREATE TABLE employees (
    emp_id INT,  
    emp_name VARCHAR(255), 
    salary FLOAT,        
    hire_date DATE,                            
    Location TEXT
);
```

### 1.2. IPL_Teams Table

```sql
CREATE TABLE ipl_teams (
    team_id INT,
    team_name VARCHAR(100),        
    home_city VARCHAR(100),                
    championships_won SMALLINT,    
    established_year YEAR
);
```

---

## 2. Tasks on the Employees Table

### 2.1. Add New Columns
- **Task 1:** Add a new column "DOJ" (Date of Joining)
- **Task 2:** Add two new columns "Phone_Number" and "email"

```sql
ALTER TABLE employees 
    ADD COLUMN DOJ DATE,
    ADD COLUMN phone_number VARCHAR(20),
    ADD COLUMN email VARCHAR(50);
```

---

### 2.2. Drop Columns
- **Task 1:** Drop the column "Location"
- **Task 2:** Drop two columns "email" and "phone_number"

```sql
-- Drop the "Location" column:
ALTER TABLE employees DROP COLUMN Location;

-- Drop the "email" and "phone_number" columns:
ALTER TABLE employees  
    DROP COLUMN email,  
    DROP COLUMN phone_number;
```

---

### 2.3. Modify Column Data Types
- **Task 1:** Modify the `salary` column data type from FLOAT to DECIMAL(10,2)
- **Task 2:** Reduce the `emp_name` size to 150 characters

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2),
    MODIFY emp_name VARCHAR(150) NOT NULL;
```

---

### 2.4. Rename Column Names
- **Task 1:** Rename the column `hire_date` to `joining_date`
- **Task 2:** Rename the column `Location` to `address`

> **Note:** If you have already dropped the `Location` column, this step would not be applicable.

```sql
-- Rename hire_date to joining_date:
ALTER TABLE employees 
    CHANGE COLUMN hire_date joining_date DATE;
-- Alternative syntax:
-- ALTER TABLE employees RENAME COLUMN hire_date TO joining_date;

-- Rename Location to address:
ALTER TABLE employees 
    CHANGE COLUMN Location address TEXT;
```

---

### 2.5. Rename Table Names
- **Task 1:** Rename **employees** to **staff_members**
- **Task 2:** Rename **employees** to **staff_members** and **departments** to **company_departments**

```sql
-- Rename employees to staff_members:
RENAME TABLE employees TO staff_members;

-- To rename multiple tables in one statement (assuming the "departments" table exists):
-- RENAME TABLE employees TO staff_members, departments TO company_departments;
```

---

### 2.6. Add a Primary Key
- **Task 1:** Set `emp_id` as the Primary Key
- **Task 2:** Modify `emp_id` to be AUTO_INCREMENT for automatic ID generation

```sql
-- Set emp_id as primary key:
ALTER TABLE employees ADD PRIMARY KEY (emp_id);

-- Modify emp_id to be AUTO_INCREMENT:
ALTER TABLE employees MODIFY emp_id INT AUTO_INCREMENT;
```

---

### 2.7. Add a Foreign Key
- **Task 1:** Add a new column `dept_id` to the employees table
- **Task 2:** Set `dept_id` as a FOREIGN KEY referencing `departments(dept_id)`

```sql
-- Add dept_id column:
ALTER TABLE employees ADD COLUMN dept_id INT;

-- Add the foreign key constraint:
ALTER TABLE employees 
    ADD CONSTRAINT fk_department FOREIGN KEY (dept_id) REFERENCES departments(dept_id);
```

---

### 2.8. Set Default Values for Columns
- **Task 1:** Set default `salary` as 50000
- **Task 2:** Set default `joining_date` as Current_Date

```sql
-- Set default for salary:
ALTER TABLE employees MODIFY salary DECIMAL(10,2) DEFAULT 50000;

-- Assuming join_date is already renamed, set its default value:
ALTER TABLE employees MODIFY joining_date DATE DEFAULT CURRENT_DATE;
```

---

### 2.9. Add Unique Constraints
- **Task 1:** Add a unique constraint to the `email` column
- **Task 2:** Add a unique constraint to the `phone_number` column

```sql
ALTER TABLE employees 
    ADD CONSTRAINT unique_email UNIQUE (email),
    ADD CONSTRAINT unique_phone UNIQUE (phone_number);
```

---

### 2.10. Drop Constraints
- **Task 1:** Drop the unique constraint on `email`
- **Task 2:** Drop the unique constraint on `phone_number`
- **Task 3:** Drop the Primary Key Constraint

```sql
-- Drop unique constraints (MySQL implements these as indexes):
ALTER TABLE employees 
    DROP INDEX unique_email,
    DROP INDEX unique_phone;

-- To drop the primary key (if the column is AUTO_INCREMENT, you might first modify it):
ALTER TABLE employees MODIFY emp_id INT;
ALTER TABLE employees DROP PRIMARY KEY;
```



