### 📌 **Introduction to SQL**  
🔹 **Database**: A collection of related data.  
🔹 **DBMS (Database Management System)**: A software application that helps in managing databases efficiently.  

🛠 **Example Scenario:**  
👉 *User* ➝ *Software Application* ➝ *Database (DBMS)*  

🔹 **SQL (Structured Query Language)**: A language used to interact with relational databases.  

---

### 📌 **Types of Databases** 🗃  
Databases are categorized into **two types**:  

1️⃣ **Relational Databases (RDBMS)** – Data is stored in **tables** (e.g., MySQL, Oracle).  
2️⃣ **Non-Relational Databases (NoSQL)** – Data is **not** stored in table format (e.g., MongoDB, Firebase).  

---

### 📌 **Datatypes in SQL** 📊  

📌 **1. Numeric Types**  
✔ `INT` – Integer values  
✔ `FLOAT` – Floating point numbers  
✔ `DECIMAL(precision, scale)` – Fixed-point numbers (e.g., `DECIMAL(10,2)`)  

📌 **2. Character Types**  
✔ `CHAR(size)` – Fixed-length string  
✔ `VARCHAR(size)` – Variable-length string (Allocates memory dynamically)  

📌 **3. Date Type**  
✔ `DATE` – Format: `YYYY-MM-DD`  

---

### 📌 **SQL Commands (5 Categories)** 🔥  

#### **1️⃣ DQL – Data Query Language**  
🔹 **Command:** `SELECT` – Retrieves data from a table.  

#### **2️⃣ DML – Data Manipulation Language**  
🔹 **Commands:**  
✔ `INSERT` – Adds new records.  
✔ `UPDATE` – Modifies existing records.  
✔ `DELETE` – Removes records.  

#### **3️⃣ DDL – Data Definition Language**  
🔹 **Commands:** (**CARDT**)  
✔ `CREATE` – Creates tables or databases.  
✔ `ALTER` – Modifies table structure.  
✔ `RENAME` – Renames a table.  
✔ `DROP` – Deletes a table.  
✔ `TRUNCATE` – Deletes all records but keeps the structure.  

#### **4️⃣ DCL – Data Control Language**  
🔹 **Commands:**  
✔ `GRANT` – Gives user permissions.  
✔ `REVOKE` – Removes user permissions.  

#### **5️⃣ TCL – Transaction Control Language**  
🔹 **Commands:**  
✔ `COMMIT` – Saves the transaction permanently.  
✔ `ROLLBACK` – Undoes the last transaction.  
✔ `SAVEPOINT` – Creates a rollback checkpoint.  

---

### 📌 **Basic SQL Commands** 🏗  

✅ **Create a Table**  
```sql
CREATE TABLE employee (
    emp_id INT,
    emp_name VARCHAR(50),
    salary DECIMAL(10,2),
    date_of_joining DATE,
    department VARCHAR(50)
);
```

✅ **Insert Data into a Table**  
```sql
INSERT INTO employee VALUES (101, 'Alice', 30000, '2004-01-25', 'CSE');
```

✅ **Retrieve Data**  
```sql
SELECT * FROM employee;
```

✅ **Describe Table Structure**  
```sql
DESC employee;
```

## 1️⃣ Creating Tables 🏗️

### 🎓 Students Table
```sql
CREATE TABLE students (
    student_id VARCHAR(20), 
    student_name VARCHAR(100), 
    college VARCHAR(100), 
    branch VARCHAR(100)
);
```

### 🏏 Cricket Teams Table
```sql
CREATE TABLE cricket (
    team_name VARCHAR(50), 
    no_of_matches_played INT, 
    no_of_matches_win INT, 
    no_of_matches_loss INT, 
    net_run_rate DECIMAL(5,3), 
    points INT
);
```

## 2️⃣ Inserting Data 📝

### 🔹 Inserting Records into Cricket Table
```sql
INSERT INTO cricket VALUES ('IND', 3, 3, 0, 0.715, 6);
INSERT INTO cricket VALUES ('NZ', 3, 2, 1, 0.267, 4);
INSERT INTO cricket VALUES ('BAN', 3, 0, 2, -0.443, 1);
INSERT INTO cricket VALUES ('PAK', 3, 0, 2, -1.087, 1);
```

## 3️⃣ TRUNCATE vs DROP 🚀

### 🔹 TRUNCATE (Deletes Records but Keeps Structure)
```sql
TRUNCATE TABLE table_name;
```
- Deletes all records but **keeps the table structure**.
- Example:
```sql
TRUNCATE TABLE students;
```

### 🔹 DROP (Deletes Table and Structure)
```sql
DROP TABLE table_name;
```
- **Deletes the table along with its structure**.
- Example:
```sql
DROP TABLE students;
```

### 🔍 View All Tables in a Database
```sql
SHOW TABLES;
```
