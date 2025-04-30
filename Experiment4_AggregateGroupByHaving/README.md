# NAME: AVINASH T
# REG_NO : 212223230026
# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**


![image](https://github.com/user-attachments/assets/0a1f1a04-8423-4df7-b807-60a43250d89b)

```sql
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

![image](https://github.com/user-attachments/assets/e85fddbd-ec56-4865-ae5b-d8e7523c8acf)


**Question 2**

![image](https://github.com/user-attachments/assets/61b71084-fc49-4b2a-9b06-e60da37b9ab8)


```sql
SELECT PatientID, COUNT(*) AS TotalMedications
FROM Prescriptions
GROUP BY PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/a8d3ea81-0fdd-411e-8cab-933a622278e1)


**Question 3**


![image](https://github.com/user-attachments/assets/be93d115-d0b1-44a7-89cc-d874219db91d)


```sql
SELECT
 Specialty,
 ROUND(AVG(
 CAST(STRFTIME('%Y','now') AS INTEGER) -
 CAST(STRFTIME('%Y',DateofBirth)as INTEGER) -
 (STRFTIME('%m -%d','now')<strftime('%m - %d',DateofBirth))),0)
AS AvgAge
FROM
 Doctors
GROUP BY
 Specialty;
```

**Output:**

![image](https://github.com/user-attachments/assets/c251b7b7-5a11-47f5-b203-66a29c01a43f)

**Question 4**

![image](https://github.com/user-attachments/assets/6ff5ad94-770c-4933-9f26-aaf58103c044)

```sql
Select sum(purch_amt) as TOTAL from
orders;
```

**Output:**


![image](https://github.com/user-attachments/assets/32432fce-1a21-4e91-8fec-ab8588428886)


**Question 5**

![image](https://github.com/user-attachments/assets/96e76155-b722-472d-bef7-5c9b74206220)

```sql
select sum(workhour) as "Total working hours" from
employee1;
```

**Output:**

![image](https://github.com/user-attachments/assets/44f2460c-91fe-486c-99a8-a286d78866fb)


**Question 6**


![image](https://github.com/user-attachments/assets/ed493cb1-ec98-4a3e-a1f2-96e95b82125f)


```sql
SELECT COUNT(*) AS COUNT 
FROM employee
WHERE age>32;
```

**Output:**

![image](https://github.com/user-attachments/assets/c350876f-a09b-40d3-879f-76ba99d3626c)


**Question 7**

![image](https://github.com/user-attachments/assets/cd347cd3-e250-4dda-bf33-da77c04aa30a)


```sql
SELECT COUNT(*) AS COUNT 
FROM customer
WHERE city = 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/4cbf4ce1-8525-47c3-86b3-a5f3312ac57a)



**Question 8**

![image](https://github.com/user-attachments/assets/83282793-7348-4642-985f-e7cc4832f03d)



```sql
Select address, AVG(salary) as "AVG(salary)"
from customer1
group by address
having avg(salary)>5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/705f33d9-f0a5-4ec8-b6b5-5089d084cd67)


**Question 9**

![image](https://github.com/user-attachments/assets/f4f0e155-dda0-4850-8e1b-4e6119991849)


```sql
select category_id,
    sum(price * category_id) as Revenue
from products
group by category_id
having sum(price * category_id) > 25;
```

**Output:**

![image](https://github.com/user-attachments/assets/c2aa2790-c749-4b1e-86a3-d6b2322481b1)


**Question 10**

![image](https://github.com/user-attachments/assets/dd11b854-3a95-4a10-aca8-d57ccc6000be)


```sql
SELECT age,
    AVG(INCOME) as "AVG(income)"
from employee
group by age
having avg(income) between 300000 and 500000;
```

**Output:**

![image](https://github.com/user-attachments/assets/0abb7574-d76b-4dcf-93d2-35c654b4c37e)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
