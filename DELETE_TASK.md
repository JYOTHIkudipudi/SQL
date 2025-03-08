# Students Table SQL Queries _ Performing DELETE Operation 

## 1. Create the Students Table

```sql
CREATE TABLE Students (
    Roll_Number VARCHAR(50) PRIMARY KEY,
    First_Name VARCHAR(50) NOT NULL,
    Last_Name VARCHAR(50) NOT NULL,
    Branch VARCHAR(100),
    College VARCHAR(150),
    Passout_Year YEAR,
    Gender VARCHAR(50),
    Date_Of_Birth DATE,
    Fee DECIMAL(10,2),
    Mobile_Number VARCHAR(15) UNIQUE
);
```

## 2. Insert Values into the Students Table

```sql
INSERT INTO Students (Roll_Number, First_Name, Last_Name, Branch, College, Passout_Year, Gender, Date_Of_Birth, Fee, Mobile_Number) VALUES
('24A91A0101', 'Rohan', 'Sharma', 'CSE', 'AEC', 2028, 'Male', '2007-03-14', 75000.00, '9876543601'),
('24P31A0102', 'Ishika', 'Verma', 'IT', 'ACET', 2028, 'Female', '2007-07-22', 72050.50, '9876543602'),
('24MH1A0103', 'Aditya', 'Patil', 'AIML', 'ACOE', 2028, 'Male', '2007-11-10', 78050.75, '9876543603'),
('24A91A0104', 'Megha', 'Rao', 'DS', 'AUS', 2028, 'Female', '2007-05-18', 69050.00, '9876543604'),
('23A91A0105', 'Aryan', 'Kapoor', 'IOT', 'AEC', 2027, 'Male', '2006-02-25', 76000.25, '9876543605'),
('23P31A0106', 'Sanya', 'Joshi', 'ECE', 'ACET', 2027, 'Female', '2006-06-28', 73000.00, '9876543606'),
('23MH1A0107', 'Kunal', 'Singh', 'EEE', 'ACOE', 2027, 'Male', '2006-04-12', 77000.50, '9876543607'),
('23A91A0108', 'Anjali', 'Desai', 'MECH', 'AUS', 2027, 'Female', '2006-09-03', 71000.00, '9876543608'),
('22A91A0109', 'Vikash', 'Nair', 'CIVIL', 'AEC', 2026, 'Male', '2005-04-10', 74000.75, '9876543609'),
('22P31A0110', 'Nikita', 'Menon', 'CSE', 'ACET', 2026, 'Female', '2005-02-28', 75050.25, '9876543610'),
('22MH1A0111', 'Aman', 'Chopra', 'IT', 'ACOE', 2026, 'Male', '2005-10-14', 78075.00, '9876543611'),
('22A91A0112', 'Tanya', 'Mishra', 'DS', 'AUS', 2026, 'Female', '2005-12-19', 69025.50, '9876543612'),
('21A91A0113', 'Rajat', 'Gupta', 'CSE', 'AEC', 2025, 'Male', '2004-07-05', 75500.00, '9876543613'),
('21P31A0114', 'Sakshi', 'Reddy', 'AIML', 'ACET', 2025, 'Female', '2004-03-15', 73050.25, '9876543614'),
('21MH1A0115', 'Nishant', 'Shetty', 'IOT', 'ACOE', 2025, 'Male', '2004-08-25', 76500.75, '9876543615'),
('21A91A0116', 'Pooja', 'Bhat', 'EEE', 'AUS', 2025, 'Female', '2004-10-30', 71050.00, '9876543616'),
('24A91A0117', 'Rahul', 'Kumar', 'MECH', 'AEC', 2028, 'Male', '2007-09-14', 74800.50, '9876543617'),
('24P31A0118', 'Simran', 'Shah', 'CIVIL', 'ACET', 2028, 'Female', '2007-05-10', 75025.00, '9876543618'),
('24MH1A0119', 'Dev', 'Tiwari', 'CSE', 'ACOE', 2028, 'Male', '2007-12-12', 77900.75, '9876543619'),
('24A91A0120', 'Kriti', 'Malhotra', 'IT', 'AUS', 2028, 'Female', '2007-06-06', 69500.00, '9876543620'),
('24A91A0121', 'Harsh', 'Pandey', 'CSE', 'AEC', 2028, 'Male', '2007-04-12', 75000.00, '9876543701'),
('24P31A0122', 'Sanya', 'Mishra', 'IT', 'ACET', 2028, 'Female', '2007-08-20', 72500.50, '9876543702'),
('24MH1A0123', 'Raghav', 'Verma', 'AIML', 'ACOE', 2028, 'Male', '2007-12-05', 78000.75, '9876543703'),
('24A91A0124', 'Meera', 'Iyer', 'DS', 'AUS', 2028, 'Female', '2007-06-15', 69000.00, '9876543704'),
('23A91A0125', 'Yash', 'Patel', 'IOT', 'AEC', 2027, 'Male', '2006-02-10', 76000.25, '9876543705'),
('23P31A0126', 'Aditi', 'Chatterjee', 'ECE', 'ACET', 2027, 'Female', '2006-05-28', 73500.00, '9876543706'),
('23MH1A0127', 'Rohit', 'Kulkarni', 'EEE', 'ACOE', 2027, 'Male', '2006-07-19', 77000.50, '9876543707'),
('23A91A0128', 'Pallavi', 'Sharma', 'MECH', 'AUS', 2027, 'Female', '2006-11-30', 71000.00, '9876543708'),
('22A91A0129', 'Siddharth', 'Nair', 'CIVIL', 'AEC', 2026, 'Male', '2005-04-07', 74000.75, '9876543709'),
('22P31A0130', 'Neha', 'Menon', 'CSE', 'ACET', 2026, 'Female', '2005-09-25', 75050.25, '9876543710'),
('22MH1A0131', 'Anurag', 'Gupta', 'IT', 'ACOE', 2026, 'Male', '2005-12-14', 78075.00, '9876543711'),
('22A91A0132', 'Tara', 'Malhotra', 'DS', 'AUS', 2026, 'Female', '2005-03-09', 69025.50, '9876543712'),
('21A91A0133', 'Vivek', 'Tiwari', 'CSE', 'AEC', 2025, 'Male', '2004-07-22', 75500.00, '9876543713'),
('21P31A0134', 'Swati', 'Reddy', 'AIML', 'ACET', 2025, 'Female', '2004-01-10', 73050.25, '9876543714'),
('21MH1A0135', 'Pranav', 'Joshi', 'IOT', 'ACOE', 2025, 'Male', '2004-10-29', 76500.75, '9876543715'),
('21A91A0136', 'Sneha', 'Bhat', 'EEE', 'AUS', 2025, 'Female', '2004-12-02', 71050.00, '9876543716'),
('24A91A0137', 'Karthik', 'Kumar', 'MECH', 'AEC', 2028, 'Male', '2007-09-15', 74800.50, '9876543717'),
('24P31A0138', 'Ishani', 'Shah', 'CIVIL', 'ACET', 2028, 'Female', '2007-05-05', 75025.00, '9876543718');
```

## SQL Queries to Delete Students

1. **Delete all students belonging to the "CSE" branch.**
```sql
DELETE FROM Students WHERE Branch = 'CSE';   --Delete all students from "AEC" & "ACET" College.
 ```
2. **Delete all students from "AEC" & "ACET" College.**
``` sql
DELETE FROM Students WHERE College IN ('AEC', 'ACET');  -- Delete all students who passed out in 2026.
 ```
3. **Delete all students who passed out in 2026.**
```sql
DELETE FROM Students WHERE Passout_Year = 2026;  --Delete all students born before 2000.
``` 
4. **Delete all students born before 2000.**
``` sql
DELETE FROM Students WHERE Date_Of_Birth < '2000-01-01'; ---Delete all students except those from the "Mechanical" branch.
```
5. **Delete all students except those from the "Mechanical" branch.**
``` sql
DELETE FROM Students WHERE Branch <> 'MECH';    --- Delete students whose last name is "Kumar".
```
6. **Delete students whose last name is "Kumar".**
``` sql
DELETE FROM Students WHERE Last_Name = 'Kumar';   -- Delete all students who belong to either "CIVIL" or "MECH" branch.
```
7. **Delete all students who belong to either "CIVIL" or "MECH" branch.**
``` sql
DELETE FROM Students WHERE Branch IN ('CIVIL', 'MECH');   ---Delete students who have a fee greater than 73000.
```
8. **Delete students who have a fee greater than 73000.**
``` sql
DELETE FROM Students WHERE Fee > 73000;   ---Delete students who were born in the year 2004.
```
9. **Delete students who were born in the year 2004.**
``` sql
DELETE FROM Students WHERE YEAR(Date_Of_Birth) = 2004;   ---Delete students from "AUS" who belong to the "CSE" branch.
```
10. **Delete students from "AUS" who belong to the "CSE" branch.**
``` sql
DELETE FROM Students WHERE College = 'AUS' AND Branch = 'CSE';
```




























































































