
## 1. Initial Table Definitions

Before we perform any modifications, we start with the original table definitions.

### 1.1. Employees Table

The `employees` table contains the following columns:
- `emp_id` (an integer identifier)
- `emp_name` (employee name)
- `salary` (employee salary stored as FLOAT)
- `hire_date` (date of hiring)
- `Location` (employee location as text)

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

The `ipl_teams` table (for illustration) has:
- `team_id`
- `team_name`
- `home_city`
- `championships_won`
- `established_year`

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

The following tasks demonstrate how to alter the `employees` table.

### 2.1. Adding New Columns

**Objective:**  
- Add a new column `DOJ` (Date of Joining).  
- Add two new columns: `phone_number` and `email`.

**Explanation:**  
These commands use the `ALTER TABLE ... ADD COLUMN` statement to introduce new fields.

```sql
ALTER TABLE employees 
    ADD COLUMN DOJ DATE,
    ADD COLUMN phone_number VARCHAR(20),
    ADD COLUMN email VARCHAR(50);
```

---

### 2.2. Dropping Columns

**Objective:**  
- Drop the column `Location`.  
- Drop the columns `email` and `phone_number`.

**Explanation:**  
To remove columns that are no longer needed, we use the `ALTER TABLE ... DROP COLUMN` command.  
*Note:* If you drop the `Location` column first, you cannot later rename it.

```sql
-- To drop the Location column:
ALTER TABLE employees DROP COLUMN Location;

-- Alternatively, to drop the email and phone_number columns:
ALTER TABLE employees  
    DROP COLUMN email,  
    DROP COLUMN phone_number;
```

---

### 2.3. Modifying Column Data Types

**Objective:**  
- Change `salary` from FLOAT to DECIMAL(10,2) for more precision.  
- Reduce the size of `emp_name` to 150 characters.

**Explanation:**  
The `MODIFY` clause is used to change the data type and constraints of a column.

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2),
    MODIFY emp_name VARCHAR(150) NOT NULL;
```

---

### 2.4. Renaming Columns

**Objective:**  
- Rename `hire_date` to `joining_date`.  
- Rename `Location` to `address`.

**Explanation:**  
The `CHANGE COLUMN` command (or `RENAME COLUMN` in newer MySQL versions) allows you to change the column name and optionally its data type.

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

### 2.5. Renaming the Table

**Objective:**  
- Rename the `employees` table to `staff_members`.  
- Optionally, rename both `employees` and `departments` (if the departments table exists) in one statement.

**Explanation:**  
The `RENAME TABLE` statement allows you to change table names.

```sql
-- Rename employees to staff_members:
RENAME TABLE employees TO staff_members;

-- To rename multiple tables:
-- RENAME TABLE employees TO staff_members, departments TO company_departments;
```

---

### 2.6. Adding a Primary Key

**Objective:**  
- Set `emp_id` as the Primary Key.  
- Modify `emp_id` to be AUTO_INCREMENT for automatic ID generation.

**Explanation:**  
A primary key uniquely identifies rows. The AUTO_INCREMENT attribute automatically generates a unique number.

```sql
-- Set emp_id as the primary key:
ALTER TABLE employees ADD PRIMARY KEY (emp_id);

-- Modify emp_id to be AUTO_INCREMENT:
ALTER TABLE employees MODIFY emp_id INT AUTO_INCREMENT;
```

---

### 2.7. Adding a Foreign Key

**Objective:**  
- Add a new column `dept_id` to the employees table.  
- Set `dept_id` as a FOREIGN KEY referencing the `departments` table.

**Explanation:**  
This demonstrates how to enforce referential integrity between tables. Ensure that the referenced table (`departments`) exists with a matching column (e.g., `dept_id`).

```sql
-- Add dept_id column:
ALTER TABLE employees ADD COLUMN dept_id INT;

-- Add the foreign key constraint:
ALTER TABLE employees 
    ADD CONSTRAINT fk_department FOREIGN KEY (dept_id) REFERENCES departments(dept_id);
```

---

### 2.8. Setting Default Values for Columns

**Objective:**  
- Set default value of `salary` to 50000.  
- Set default value of `joining_date` to the current date.

**Explanation:**  
Default values are assigned automatically when no value is specified during insertion.

```sql
ALTER TABLE employees 
    MODIFY salary DECIMAL(10,2) DEFAULT 50000;

-- Assuming join_date was already renamed:
ALTER TABLE employees 
    MODIFY joining_date DATE DEFAULT CURRENT_DATE;
```

---

### 2.9. Adding Unique Constraints

**Objective:**  
- Add a unique constraint to the `email` column.  
- Add a unique constraint to the `phone_number` column.

**Explanation:**  
Unique constraints ensure that the values in a column are distinct across all rows.

```sql
ALTER TABLE employees 
    ADD CONSTRAINT unique_email UNIQUE (email),
    ADD CONSTRAINT unique_phone UNIQUE (phone_number);
```

---

### 2.10. Dropping Constraints

**Objective:**  
- Drop the unique constraint on `email`.  
- Drop the unique constraint on `phone_number`.  
- Drop the primary key constraint.

**Explanation:**  
In MySQL, unique constraints are implemented as indexes. The `DROP INDEX` command is used for them, and `DROP PRIMARY KEY` removes the primary key.

```sql
-- Drop unique constraints:
ALTER TABLE employees 
    DROP INDEX unique_email,
    DROP INDEX unique_phone;

-- Drop the primary key:
ALTER TABLE employees 
    DROP PRIMARY KEY;
```

> **Important:**  
> If the primary key column is set to AUTO_INCREMENT, you might need to remove the AUTO_INCREMENT attribute before dropping the primary key.

  
