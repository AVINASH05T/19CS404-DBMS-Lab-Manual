## NAME : AVINASH T
## REG_NO : 212223230026
# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

![image](https://github.com/user-attachments/assets/d115dc2d-a7ba-4b6d-8d37-98312c844e55)



```sql
SELECT * FROM  CUSTOMERS WHERE ID IN (SELECT ID FROM CUSTOMERS WHERE ADDRESS='Delhi' AND AGE<300);
```

**Output:**


![image](https://github.com/user-attachments/assets/891da76a-6a77-40c8-8b9d-a1f7d6d26e79)



**Question 2**

![image](https://github.com/user-attachments/assets/c8d2f50e-aedc-40e1-9582-2cbeaaf9f5d5)


```sql
SELECT * FROM Orders WHERE salesman_id IN (SELECT salesman_id FROM Salesman WHERE city = 'New York');
```

**Output:**

![image](https://github.com/user-attachments/assets/4e0c8de2-c3f8-4869-95fa-0d6c9efc2d8d)


**Question 3**


![image](https://github.com/user-attachments/assets/3704f301-c4f7-4ec3-b136-9e7362140f25)


```sql
-- Paste your SQL code below for Question 3
```

**Output:**

![Output3](output.png)

**Question 4**

![image](https://github.com/user-attachments/assets/122c61df-08b6-46f6-83d0-019661e1b549)


```sql
SELECT salesman_id, name
FROM salesman
WHERE salesman_id IN (
    SELECT salesman_id
    FROM customer
    GROUP BY salesman_id
    HAVING COUNT(customer_id) > 1
);

```

**Output:**

![image](https://github.com/user-attachments/assets/bc68b589-2266-48d0-9e6a-30d3fd8d89ee)


**Question 5**

![image](https://github.com/user-attachments/assets/95fdf15e-c59b-433d-9ab1-03200aee272b)


```sql
select * from Orders where salesman_id in (select salesman_id from Orders where customer_id=3007);
```

**Output:**

![image](https://github.com/user-attachments/assets/cce4ca8f-e5b3-4b8e-8a24-af30b9c85f65)


**Question 6**

![image](https://github.com/user-attachments/assets/de7971ff-e036-458c-ac41-dab7c2ecfd0b)


```sql
SELECT * FROM Orders WHERE salesman_id IN (SELECT salesman_id FROM Salesman WHERE city = 'London');
```

**Output:**

![image](https://github.com/user-attachments/assets/3bea5ded-562c-4ac5-961b-e40da7f843c7)


**Question 7**

![image](https://github.com/user-attachments/assets/e77fe728-6d2f-4655-97bf-e664b92540a5)


```sql
SELECT * FROM CUSTOMERS WHERE ID IN (SELECT ID FROM CUSTOMERS WHERE SALARY > 4500 );
```

**Output:**

![image](https://github.com/user-attachments/assets/86b3cea8-dc86-48fa-afd2-b2f6f53ac073)


**Question 8**

![image](https://github.com/user-attachments/assets/68885042-2ed1-42ca-aaa8-3e712f579a9e)


```sql
SELECT student_name,grade FROM GRADES G WHERE grade = (SELECT min(grade) FROM GRADES WHERE subject=G.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/57055d25-eafc-4440-889c-b01da2f7cbaa)


**Question 9**

![image](https://github.com/user-attachments/assets/f1a71a8f-99f0-40f3-920a-0ae9867b3ba2)

```sql
select ord_no,purch_amt,ord_date,salesman_id from Orders where salesman_id in (select salesman_id from salesman where commission =( select  max(commission) from salesman) )
```

**Output:**

![image](https://github.com/user-attachments/assets/21b34702-b7a3-48a3-ab32-d692cf670b90)


**Question 10**


![image](https://github.com/user-attachments/assets/c09fda56-a0dd-445d-86d9-6aeeeef79dff)


```sql
SELECT * FROM CUSTOMERS WHERE ID IN (SELECT ID FROM CUSTOMERS WHERE SALARY = 1500 );
```

**Output:**

![image](https://github.com/user-attachments/assets/bc751e87-a9e6-4692-bcc1-9b57ea45b919)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
