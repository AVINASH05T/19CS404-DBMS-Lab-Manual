# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**

![image](https://github.com/user-attachments/assets/67a12bdb-7247-4db9-a566-742efcc46216)


```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES(2,'John Smith','Developer','IT',75000);
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

![image](https://github.com/user-attachments/assets/fc919405-ab15-49ba-9b5f-b5bce79b7b20)


**Question 2**

![image](https://github.com/user-attachments/assets/c1b89dc0-fdd7-4f52-9b7a-fdb51bb51dad)
```sql
CREATE TABLE jobs(
job_id INTEGER PRIMARY KEY,
job_title TEXT DEFAULT '',
min_salary INTEGER DEFAULT 8000,
max_salary INTEGER DEFAULT NULL
);
```

**Output:**
![image](https://github.com/user-attachments/assets/24748945-ea54-4a15-9804-0437ce94834d)


**Question 3**

![image](https://github.com/user-attachments/assets/e10c4011-ab8d-4ab1-9c76-8efb39d26c72)


```sql
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE
);
```

**Output:**
![image](https://github.com/user-attachments/assets/a42cd9c9-b621-46c8-aa90-1654bc3a48d3)




**Question 4**

![image](https://github.com/user-attachments/assets/5c106c88-efac-4283-9609-6421bf659773)


**Question 5**
![image](https://github.com/user-attachments/assets/87f0aee8-1aa6-4f38-abef-704b78da9f40)


```sql
CREATE TABLE ProjectAssignments(
AssignmentID  int PRIMARY KEY,
EmployeeID int,
ProjectID int,
AssignmentDate date NOT NULL,
foreign key (EmployeeID)references Employees(EmployeeID),
foreign key (ProjectID)references Projects(ProjectID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/af3c08b3-032a-4025-9244-cf0ad2e78f39)



**Question 6**

 ![image](https://github.com/user-attachments/assets/9b7a1550-d378-468f-86b9-682051836142)


```sql
CREATE TABLE Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE ,
DueDate DATE CHECK(DueDate > InvoiceDate),
Amount REAL  CHECK(Amount > 0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/04c21ed5-2834-4b32-8f1c-00aa0c089541)


**Question 7**
![image](https://github.com/user-attachments/assets/5c461205-abab-4c88-aa2d-6689cbf2f553)


**Question 8**

![image](https://github.com/user-attachments/assets/d0dddb24-b633-4e20-b22e-c3e6d9138e54)


```sql
CREATE TABLE Employees(
EmployeeID INT primary key,
FirstName VARCHAR(50) NOT NULL,
LastName VARCHAR(50) NOT NULL,
Email VARCHAR(50) UNIQUE,
Salary DECIMAL (10,2) CHECK(Salary > 0),
DepartmentID INT,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/212de811-c259-4292-9858-74b375c74f3d)


**Question 9**

![image](https://github.com/user-attachments/assets/199b0a4d-3749-4485-97c3-142a79d4d001)



```sql
ALTER TABLE employee RENAME COLUMN id TO employee_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/05236aca-6d28-4b42-9b2b-d38cf978e521)



**Question 10**

![image](https://github.com/user-attachments/assets/637afe1b-54b8-43b4-8f7c-0791f524e7f6)


```sql
ALTER TABLE books ADD COLUMN ISBN varchar(30);
ALTER TABLE books ADD COLUMN domain_dept varchar(30);
```

**Output:**

![image](https://github.com/user-attachments/assets/c78e258b-eda1-4842-a859-9ebe7de5bc1f)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
