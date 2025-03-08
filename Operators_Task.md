 # SQL Queries - `WHERE` Clause

## 1. Creating the `employees` Table

To create an `employees` table in MySQL, use the following query:

```sql
CREATE TABLE employees (
    Emp_ID INT PRIMARY KEY,
    Emp_Name VARCHAR(100) ,
    Designation VARCHAR(100),
    Department VARCHAR(100) ,
    Email VARCHAR(150) UNIQUE,
    Date_Of_Joining DATE ,
    Gender VARCHAR (50),
    Date_Of_Birth DATE,
    Salary DECIMAL(10,2),
    Mobile_Number VARCHAR(15) UNIQUE
);
```



## 2. Inserting Data into `employees` Table

Use the following query to insert employee records:

```sql
INSERT INTO employees (Emp_ID,EMP_Name, Designation, Department, Email, Date_Of_Joining, Gender, Date_Of_Birth, Salary, Mobile_Number) VALUES
(1,'Amit Sharma', 'Software Engineer', 'IT', 'amit.sharma@example.com', '2020-05-10', 'Male', '1995-08-15', 75000.00, '9876543210'),
(2,'Priya Verma', 'HR Manager', 'HR', NULL, '2018-07-22', 'Female', '1990-02-18', 85000.00, '9876543211'),
(3,'Rahul Mehta', 'Marketing Executive', 'Marketing', 'rahul.mehta@example.com', '2019-03-15', 'Male', NULL, 60000.00, '9876543212'),
(4,'Sneha Kapoor', 'Finance Analyst', 'Finance', 'sneha.kapoor@example.com', '2021-01-05', NULL, '1996-11-30', 72000.00, '9876543213'),
(5,'Arjun Singh', 'Project Manager', 'IT', 'arjun.singh@example.com', NULL, 'Male', '1988-04-12', 95000.00, '9876543214'),
(6,'Neha Gupta', 'Software Tester', 'IT', 'neha.gupta@example.com', '2022-02-20', 'Female', '1997-09-08', NULL, '9876543215'),
(7,'Rohan Bhatia', 'HR Executive', 'HR', 'rohan.bhatia@example.com', '2020-11-18', 'Male', '1994-07-20', 55000.00, NULL),
(8,'Ankita Das', NULL, 'Business', 'ankita.das@example.com', '2016-06-14', 'Female', '1989-05-25', 90000.00, '9876543217'),
(9,'Vikram Chauhan', 'Sales Manager', 'Sales', 'vikram.chauhan@example.com', '2015-10-05', 'Male', '1985-12-01', NULL, '9876543218'),
(10,'Simran Kaur', 'Content Writer', 'Marketing', NULL, '2021-08-11', 'Female', '1998-03-22', 50000.00, '9876543219'),
(11,'Manoj Tiwari', 'Network Engineer', NULL, 'manoj.tiwari@example.com', '2019-12-30', 'Male', '1991-06-05', 82000.00, '9876543220'),
(12,'Kavita Nair', 'Graphic Designer', 'Design', 'kavita.nair@example.com', '2020-04-08', 'Female', NULL, 65000.00, '9876543221'),
(13,'Suresh Reddy', 'Operations Manager', 'Operations', 'suresh.reddy@example.com', '2014-03-27', 'Male', '1984-02-15', 99000.00, '9876543222'),
(14,'Megha Choudhary', 'Data Scientist', 'IT', 'megha.choudhary@example.com', '2022-03-18', 'Female', '1995-12-25', 89000.00, '9876543223'),
(15,'Aditya Malhotra', 'Digital Marketing Manager', 'Marketing', 'aditya.malhotra@example.com', '2018-01-09', 'Male', NULL, 87000.00, '9876543224'),
(16,'Tanya Bose', 'UI/UX Designer', 'Design', 'tanya.bose@example.com', '2021-07-15', NULL, '1993-04-30', 70000.00, '9876543225'),
(17,'Rajesh Iyer', 'Logistics Manager', 'Logistics', 'rajesh.iyer@example.com', '2015-05-21', 'Male', '1987-11-02', NULL, '9876543226'),
(18,'Pooja Aggarwal', 'Customer Support Lead', 'Customer Support', NULL, '2019-09-12', 'Female', '1991-01-14', 72000.00, '9876543227'),
(19,'Ankit Goel', 'Software Developer', 'IT', 'ankit.goel@example.com', '2023-02-01', 'Male', '1999-07-10', NULL, NULL),
(20,'Swati Kulkarni', 'Accountant', 'Finance', 'swati.kulkarni@example.com', '2017-08-05', 'Female', NULL, NULL, '9876543229'),
(21,'Abhishek Kumar', 'Software Engineer', 'IT', 'abhishek.kumar@example.com', '2022-10-12', 'Male', '1996-07-19', 72000.00, '9876543230'),
(22,'Divya Menon', 'HR Executive', 'HR', 'divya.menon@example.com', '2020-01-08', 'Female', '1993-02-14', 58000.00, NULL),
(23,'Sunil Rathi', 'Sales Executive', 'Sales', 'sunil.rathi@example.com', '2019-06-25', 'Male', NULL, 62000.00, '9876543232'),
(24,'Neeraj Mishra', 'Network Engineer', 'IT', NULL, '2021-12-10', 'Male', '1994-09-27', NULL, '9876543233'),
(25,'Asha Nair', 'Finance Executive', 'Finance', 'asha.nair@example.com', '2018-11-30', 'Female', NULL, 78000.00, '9876543234'),
(26,'Ravi Shetty', 'Operations Coordinator', 'Operations', 'ravi.shetty@example.com', '2017-04-18', 'Male', '1989-06-21', NULL, NULL),
(27,'Poonam Sinha', 'Marketing Analyst', 'Marketing', NULL, '2022-02-15', 'Female', '1997-01-10', 65000.00, '9876543236'),
(28,'Nikhil Kapoor', 'Data Scientist', 'IT', 'nikhil.kapoor@example.com', '2023-07-22', 'Male', '1998-10-05', 90000.00, '9876543237'),
(29,'Shruti Malhotra', 'UI/UX Designer', 'Design', 'shruti.malhotra@example.com', '2021-05-09', NULL, '1995-03-22', 72000.00, '9876543238'),
(30,'Karan Verma', 'Business Analyst', 'Business', 'karan.verma@example.com', '2016-09-14', 'Male', NULL, 85000.00, '9876543239'),
(31,'Tina DSouza', 'Customer Support', 'Customer Support', 'tina.dsouza@example.com', NULL, 'Female', '1992-08-15', 60000.00, '9876543240'),
(32,'Sanjay Gupta', 'Software Developer', 'IT', 'sanjay.gupta@example.com', '2019-12-01', 'Male', NULL, NULL, '9876543241'),
(33,'Monika Jain', 'HR Assistant', 'HR', 'monika.jain@example.com', '2020-10-20', 'Female', '1993-07-17', 54000.00, '9876543242'),
(34,'Rajiv Tiwari', 'Marketing Manager', 'Marketing', NULL, '2017-03-15', 'Male', '1988-05-28', 88000.00, NULL),
(35,'Snehal Patil', 'Finance Analyst', 'Finance', 'snehal.patil@example.com', '2021-06-05', 'Female', NULL, 78000.00, '9876543244'),
(36,'Vishal Saxena', 'Project Manager', 'IT', 'vishal.saxena@example.com', NULL, 'Male', '1987-11-11', 97000.00, '9876543245'),
(37,'Ritu Chawla', 'Content Strategist', 'Marketing', 'ritu.chawla@example.com', '2020-12-25', 'Female', '1991-04-09', NULL, '9876543246'),
(38,'Kunal Mehta', 'Operations Manager', 'Operations', 'kunal.mehta@example.com', '2015-08-14', 'Male', NULL, 99000.00, '9876543247'),
(39,'Alisha Grover', 'Graphic Designer', 'Design', NULL, '2019-07-01', 'Female', '1996-12-30', 67000.00, '9876543248'),
(40,'Ramesh Yadav', 'Software Tester', 'IT', 'ramesh.yadav@example.com', '2022-11-18', 'Male', '1997-06-15', NULL, '9876543249'),
(41,'Manisha Kapoor', 'Business Consultant', 'Business', 'manisha.kapoor@example.com', '2018-05-30', 'Female', NULL, 92000.00, NULL),
(42,'Saurabh Sharma', 'Sales Executive', 'Sales', NULL, '2019-10-10', 'Male', '1995-08-20', 61000.00, '9876543251'),
(43,'Priyanka Joshi', 'Account Manager', 'Finance', 'priyanka.joshi@example.com', '2021-09-14', 'Female', NULL, 79000.00, '9876543252'),
(44,'Naveen Reddy', 'Customer Support Lead', 'Customer Support', 'naveen.reddy@example.com', '2016-02-19', 'Male', '1991-03-07', 74000.00, NULL),
(45,'Kritika Bansal', 'Data Analyst', 'IT', 'kritika.bansal@example.com', NULL, 'Female', '1994-07-09', 88000.00, '9876543254'),
(46,'Rahul Sen', 'Product Manager', 'Business', 'rahul.sen@example.com', '2017-06-22', 'Male', NULL, NULL, '9876543255'),
(47,'Aparna Dixit', 'Digital Marketing Executive', 'Marketing', NULL, '2022-04-30', 'Female', '1998-02-25', 67000.00, '9876543256'),
(48,'Siddharth Iyer', 'DevOps Engineer', 'IT', 'siddharth.iyer@example.com', '2019-11-12', 'Male', NULL, 89000.00, '9876543257'),
(49,'Bhavya Arora', 'HR Recruiter', 'HR', 'bhavya.arora@example.com', '2023-01-15', 'Female', '1999-05-11', NULL, '9876543258'),
(50,'Vikash Singh', 'Backend Developer', 'IT', 'vikash.singh@example.com', '2020-08-07', 'Male', '1995-12-19', 80000.00, NULL),
(51,'Amitabh Rao', 'Software Engineer', 'IT', 'amitabh.rao@example.com', '2019-04-15', 'Male', '1995-09-12', 78000.00, '9876543259'),
(52,'Ritika Sinha', 'HR Coordinator', 'HR', NULL, '2021-06-10', 'Female', '1994-02-25', 62000.00, '9876543260'),
(53,'Manish Agarwal', 'Network Security Engineer', 'IT', 'manish.agarwal@example.com', '2020-09-20', 'Male', NULL, 85000.00, '9876543261'),
(54,'Ananya Sharma', 'Finance Associate', 'Finance', 'ananya.sharma@example.com', '2018-07-07', 'Female', '1992-11-30', NULL, '9876543262'),
(55,'Prakash Deshmukh', 'Sales Executive', 'Sales', 'prakash.deshmukh@example.com', '2022-12-05', 'Male', '1997-03-22', 68000.00, NULL),
(56,'Sonia Kapoor', 'Marketing Lead', 'Marketing', 'sonia.kapoor@example.com', '2017-03-18', 'Female', NULL, 94000.00, '9876543264'),
(57,'Rajat Mehta', 'Project Coordinator', 'Operations', NULL, '2019-10-22', 'Male', '1991-08-15', NULL, '9876543265'),
(58,'Tushar Rane', 'Software Tester', 'IT', 'tushar.rane@example.com', '2023-01-12', 'Male', '1998-07-09', 73000.00, '9876543266'),
(59,'Sakshi Malhotra', 'Graphic Designer', 'Design', 'sakshi.malhotra@example.com', NULL, 'Female', '1995-05-21', 71000.00, '9876543267'),
(60,'Vikas Tyagi', 'Business Analyst', 'Business', 'vikas.tyagi@example.com', '2016-08-30', 'Male', NULL, 88000.00, '9876543268'),
(61,'Simran Kaur', 'Customer Support Executive', 'Customer Support', 'simran.kaur@example.com', '2020-04-10', 'Female', '1993-01-19', 59000.00, NULL),
(62,'Ajay Patel', 'Software Developer', 'IT', 'ajay.patel@example.com', '2019-11-05', 'Male', '1996-10-10', NULL, '9876543270'),
(63,'Meera Nambiar', 'HR Manager', 'HR', 'meera.nambiar@example.com', '2015-09-27', NULL, '1991-04-16', 91000.00, '9876543271'),
(64,'Rohit Saxena', 'Marketing Analyst', 'Marketing', 'rohit.saxena@example.com', '2018-06-12', 'Male', NULL, 77000.00, '9876543272'),
(65,'Neha Trivedi', 'Finance Officer', 'Finance', 'neha.trivedi@example.com', NULL, 'Female', '1992-09-04', NULL, '9876543273'),
(66,'Pankaj Bhardwaj', 'Operations Lead', 'Operations', 'pankaj.bhardwaj@example.com', '2022-01-25', 'Male', NULL, 96000.00, '9876543274'),
(67,'Roshni Verma', 'UI/UX Designer', 'Design', NULL, '2021-08-14', 'Female', '1997-02-13', 72000.00, '9876543275'),
(68,'Karthik Reddy', 'Backend Developer', 'IT', 'karthik.reddy@example.com', '2020-03-22', 'Male', '1995-12-27', NULL, NULL),
(69,'Sweta Bhagat', 'Sales Associate', 'Sales', 'sweta.bhagat@example.com', '2017-10-09', 'Female', NULL, 64000.00, '9876543277'),
(70,'Tarun Malhotra', 'Product Manager', 'Business', 'tarun.malhotra@example.com', '2016-11-01', 'Male', '1988-06-15', NULL, '9876543278'),
(71,'Pooja Iyer', 'Data Analyst', 'IT', 'pooja.iyer@example.com', '2019-07-13', 'Female', NULL, 86000.00, '9876543279'),
(72,'Aditya Bansal', 'Digital Marketer', 'Marketing', 'aditya.bansal@example.com', '2022-04-17', 'Male', '1999-05-29', 67000.00, '9876543280'),
(73,'Ravi Shankar', 'HR Executive', 'HR', NULL, '2021-12-28', 'Male', '1993-08-05', NULL, '9876543281'),
(74,'Deepika Khanna', 'Finance Consultant', 'Finance', 'deepika.khanna@example.com', '2018-01-30', 'Female', '1990-10-14', 89000.00, NULL),
(75,'Vivek Sethi', 'Customer Support Manager', 'Customer Support', 'vivek.sethi@example.com', '2015-06-07', 'Male', NULL, 75000.00, '9876543283'),
(76,'Nisha Sharma', 'Operations Executive', 'Operations', NULL, '2019-05-02', 'Female', '1995-03-11', 67000.00, '9876543284'),
(77,'Kunal Thakur', 'Logistics Coordinator', 'Logistics', 'kunal.thakur@example.com', '2021-11-14', 'Male', NULL, 82000.00, '9876543285'),
(78,'Pallavi Rao', 'Content Writer', 'Marketing', 'pallavi.rao@example.com', '2020-08-23', NULL, '1996-12-20', 58000.00, '9876543286'),
(79,'Sandeep Joshi', 'IT Support Engineer', 'IT', 'sandeep.joshi@example.com', NULL, 'Male', '1994-04-17', NULL, '9876543287'),
(80,'Preeti Yadav', 'Data Scientist', 'IT', 'preeti.yadav@example.com', '2018-03-19', 'Female', NULL, 91000.00, NULL),
(81,'Aarav Joshi', 'Software Engineer', 'IT', 'aarav.joshi@example.com', '2020-06-10', 'Male', '1996-02-15', 75000.00, '9876543288'),
(82,'Tanvi Mehta', 'HR Associate', 'HR', NULL, '2021-08-20', 'Female', '1994-07-11', 62000.00, '9876543289'),
(83,'Raghav Kapoor', 'Network Administrator', 'IT', 'raghav.kapoor@example.com', '2019-03-14', 'Male', NULL, 84000.00, '9876543290'),
(84,'Neha Verma', 'Finance Manager', 'Finance', 'neha.verma@example.com', '2018-10-05', 'Female', '1992-11-18', NULL, '9876543291'),
(85,'Karan Sharma', 'Sales Executive', 'Sales', 'karan.sharma@example.com', '2022-12-25', 'Male', '1997-06-09', 69000.00, NULL),
(86,'Divya Reddy', 'Marketing Manager', 'Marketing', 'divya.reddy@example.com', '2017-02-18', 'Female', NULL, 95000.00, '9876543293'),
(87,'Sameer Nair', 'Project Coordinator', 'Operations', NULL, '2019-11-12', 'Male', '1991-09-08', NULL, '9876543294'),
(88,'Pooja Bhatt', 'Software Tester', 'IT', 'pooja.bhatt@example.com', '2023-05-21', 'Female', '1998-07-28', 74000.00, '9876543295'),
(89,'Alok Tiwari', 'Data Scientist', 'IT', 'alok.tiwari@example.com', NULL, 'Male', '1995-10-11', 92000.00, '9876543296'),
(90,'Sanya Malhotra', 'UI/UX Designer', 'Design', NULL, '2021-07-01', 'Female', '1996-03-05', 72000.00, '9876543297'),
(91,'Nishant Gupta', 'Business Analyst', 'Business', 'nishant.gupta@example.com', '2016-06-17', 'Male', NULL, 87000.00, '9876543298'),
(92,'Meghna Desai', 'Customer Support', 'Customer Support', 'meghna.desai@example.com', '2020-04-05', 'Female', '1993-02-20', 60000.00, NULL),
(93,'Rahul Chopra', 'Software Developer', 'IT', 'rahul.chopra@example.com', '2019-12-15', 'Male', NULL, NULL, '9876543300'),
(94,'Anjali Iyer', 'HR Manager', 'HR', 'anjali.iyer@example.com', '2015-08-10', NULL, '1991-05-17', 91000.00, '9876543301'),
(95,'Vikram Singh', 'Marketing Analyst', 'Marketing', 'vikram.singh@example.com', '2018-07-23', 'Male', NULL, 77000.00, '9876543302'),
(96,'Sneha Patil', 'Finance Consultant', 'Finance', 'sneha.patil@example.com', NULL, 'Female', '1992-09-30', NULL, '9876543303'),
(97,'Rajat Rane', 'Operations Manager', 'Operations', 'rajat.rane@example.com', '2022-02-11', 'Male', NULL, 96000.00, '9876543304'),
(98,'Trisha Menon', 'Graphic Designer', 'Design', NULL, '2021-09-19', 'Female', '1997-01-14', 73000.00, '9876543305'),
(99,'Harish Reddy', 'Backend Developer', 'IT', 'harish.reddy@example.com', '2020-05-14', 'Male', '1995-12-29', NULL, NULL),
(100,'Payal Kapoor', 'Sales Associate', 'Sales', 'payal.kapoor@example.com', '2017-11-03', 'Female', NULL, 65000.00, '9876543307'),
(101,'Arun Sinha', 'Product Manager', 'Business', 'arun.sinha@example.com', '2016-10-21', 'Male', '1988-07-11', NULL, '9876543308'),
(102,'Meera Jain', 'Data Analyst', 'IT', 'meera.jain@example.com', '2019-08-04', 'Female', NULL, 86000.00, '9876543309'),
(103,'Aakash Gupta', 'Digital Marketer', 'Marketing', 'aakash.gupta@example.com', '2022-06-27', 'Male', '1999-03-25', 68000.00, '9876543310'),
(104,'Kriti Malhotra', 'HR Executive', 'HR', NULL, '2021-12-30', 'Female', '1993-10-01', NULL, '9876543311'),
(105,'Anupam Yadav', 'Finance Officer', 'Finance', 'anupam.yadav@example.com', '2018-02-05', 'Male', '1990-11-20', 89000.00, NULL),
(106,'Mohit Saxena', 'Customer Support Manager', 'Customer Support', 'mohit.saxena@example.com', '2015-04-11', 'Male', NULL, 76000.00, '9876543313'),
(107,'Shruti Das', 'Operations Executive', 'Operations', NULL, '2019-06-03', 'Female', '1995-05-02', 68000.00, '9876543314'),
(108,'Siddharth Singh', 'Logistics Manager', 'Logistics', 'siddharth.singh@example.com', '2021-12-15', 'Male', NULL, 83000.00, '9876543315'),
(109,'Poonam Bhatia', 'Content Writer', 'Marketing', 'poonam.bhatia@example.com', '2020-09-12', NULL, '1996-11-22', 59000.00, '9876543316'),
(110,'Rajesh Malhotra', 'IT Support Engineer', 'IT', 'rajesh.malhotra@example.com', NULL, 'Male', '1994-02-15', NULL, '9876543317'),
(111,'Vandana Tiwari', 'Data Scientist', 'IT', 'vandana.tiwari@example.com', '2018-04-19', 'Female', NULL, 91000.00, NULL);
  ```

### 1. Retrieve Employees in the IT department AND having a salary greater than 75,000
```sql
SELECT * FROM Employees 
WHERE Department = 'IT' AND Salary > 75000;
```

### 2. Retrieve Employees who are NOT in the Finance department.
```sql
SELECT * FROM Employees 
WHERE Department <> 'Finance';
```

### 3. Retrieve Employees with a salary greater than 70,000 but NOT from the IT department.
```sql
SELECT * FROM Employees 
WHERE Salary > 70000 AND Department <> 'IT';
```

### 4. Retrieve Employees whose salary is between 60,000 and 90,000.
```sql
SELECT * FROM Employees 
WHERE Salary BETWEEN 60000 AND 90000;
```

### 5. Retrieve Employees who joined on or after 2018-01-01.
```sql
SELECT * FROM Employees 
WHERE Join_Date >= '2018-01-01';
```

### 6. Retrieve Employees in HR or Finance department AND joined after 2019.
```sql
SELECT * FROM Employees 
WHERE (Department = 'HR' OR Department = 'Finance') AND Join_Date > '2019-01-01';
```

### 7. Retrieve Employees from IT, HR, or Finance departments.
```sql
SELECT * FROM Employees 
WHERE Department IN ('IT', 'HR', 'Finance');
```

