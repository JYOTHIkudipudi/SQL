# 📌 Introduction to SQL  

## 📚 What is a Database?
- A **database** is a collection of data 📂.
- **DBMS (Database Management System)**: A software application to manage databases 💻.
- **SQL (Structured Query Language)**: Used to interact with databases 🛠️.

## 🏛️ Types of Databases
1. **Relational Database (RDBMS)** - Uses **tables** 📊 (e.g., MySQL, Oracle).
2. **Non-Relational Database (NoSQL)** - Stores data in formats other than tables (e.g., MongoDB).

---

## 📏 Data Types in SQL
1. **Numeric**: `INT`, `FLOAT`, `DECIMAL(precision, scale)` (e.g., `DECIMAL(10,2)`) 🔢
2. **Character**: `CHAR(size)`, `VARCHAR(size)` (allocates memory dynamically) 🏷️
3. **Date**: `YYYY-MM-DD` 📅

---

## ⚡ SQL Commands (Categorized into 5 Types)
1. **DQL (Data Query Language)**: `SELECT` 🔍
2. **DML (Data Manipulation Language)**: `INSERT`, `UPDATE`, `DELETE` ✏️
3. **DDL (Data Definition Language)**: `CREATE`, `ALTER`, `RENAME`, `DROP`, `TRUNCATE` 📜
4. **DCL (Data Control Language)**: `GRANT`, `REVOKE` 🔑
5. **TCL (Transaction Control Language)**: `COMMIT`, `ROLLBACK`, `SAVEPOINT` 💾

---

## 🏗️ SQL Table Operations
### 1️⃣ Create a Table 🏠
```sql
CREATE TABLE table_name (
  col_name data_type,
  col_name2 data_type2
);
```
### 2️⃣ Insert Data 📥
```sql
INSERT INTO table_name VALUES (value1, value2, ...);
INSERT INTO table_name (col1, col2) VALUES (value1, value2);
```
Example:
```sql
INSERT INTO employee VALUES (101, 'Alice', 30000, '2004-01-25', 'CSE');
SELECT * FROM employee;
DESC employee;
```

### 3️⃣ Truncate & Drop Tables ❌
```sql
TRUNCATE TABLE table_name;  -- Deletes records but keeps structure
DROP TABLE table_name;  -- Deletes entire table with structure
SHOW TABLES;  -- View all tables
```

---

## 🔐 SQL Constraints (Rules Applied to Columns)
1. **NOT NULL**: Column cannot be empty 🚫
2. **UNIQUE**: Ensures unique values ✅
3. **DEFAULT**: Assigns a default value ⚙️
4. **CHECK**: Validates conditions before inserting ⏳
5. **PRIMARY KEY**: Combines `NOT NULL` + `UNIQUE` 🔑
6. **FOREIGN KEY**: Establishes relations between tables 🔗

### ✍️ Example: Employee Table
```sql
CREATE TABLE employee (
  emp_id INT PRIMARY KEY,
  emp_name VARCHAR(50) NOT NULL,
  salary INT NOT NULL,
  department VARCHAR(50) UNIQUE,
  age INT CHECK (age > 25)
);
```

---

## 🔧 ALTER Command (Modify Table Structure)
### ➕ Add a New Column
```sql
ALTER TABLE table_name ADD column_name datatype;
```
### ➖ Remove a Column
```sql
ALTER TABLE table_name DROP COLUMN column_name;
```
### 🔄 Rename a Table
```sql
ALTER TABLE old_table_name RENAME TO new_table_name;
```
Example:
```sql
ALTER TABLE student ADD dob DATE;
ALTER TABLE student DROP fee;
ALTER TABLE employee RENAME TO staff;
```

---

## 🧮 Operators in SQL
### ✨ Arithmetic Operators
```sql
SELECT 1000 + 23456;  -- Addition ➕
SELECT 50 % 4;  -- Modulus ➗
```
### 🔄 Relational (Comparison) Operators
```sql
SELECT (100 <= 678);  -- True (1) ✅
SELECT (100 != 678);  -- True (1) ✅
```
### 🔍 Logical Operators
```sql
SELECT (12456 >= 455890) AND (2467 <= 890);  -- False (0) ❌
SELECT NOT ((12456 >= 455890) AND (2467 <= 890));  -- True (1) ✅
```

---

## 📌 Clauses in SQL
### 🎯 WHERE Clause (Filters Records)
```sql
SELECT * FROM employees WHERE department = 'IT';
SELECT * FROM employees WHERE salary > 50000;
```
### ✏️ UPDATE Command (Modify Data)
```sql
UPDATE table_name SET col_name = 'Value1', col_name2 = value2 WHERE condition;
```
### 🗑️ DELETE Command (Remove Records)
```sql
DELETE FROM table_name WHERE condition;
DELETE FROM employees WHERE department = 'IT';
```

