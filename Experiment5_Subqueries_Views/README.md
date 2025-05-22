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
--
-- ![image](https://github.com/user-attachments/assets/9f7f8e1a-9f35-409d-8557-a016315c77ac)


```sql
-- 
SELECT *
FROM Grades g
WHERE (g.subject, g.grade) IN (
  SELECT subject, MIN(grade)
  FROM Grades
  GROUP BY subject
);

```

**Output:**

![image](https://github.com/user-attachments/assets/ba3e4777-1c05-4874-884c-95d8735c28ce)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/64767381-b09c-4200-9778-7fa00b4eb845)


```sql
-- 
SELECT name, city
FROM customer
WHERE city IN (
  SELECT city
  FROM customer
  WHERE id IN (3, 7)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/cebc3183-0425-4174-be85-45bf4f0f026a)


**Question 3**
---
![image](https://github.com/user-attachments/assets/d69dad11-4797-4dac-b9ef-4d00030be11e)

-- 

```sql
-- SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city ='New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/7cd9a460-3d33-4b05-8f87-584e66bb6c93)


**Question 4**
---
![image](https://github.com/user-attachments/assets/3a172d77-6b59-4b51-9c58-29e9871b123c)

-- 
```

SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;

-- 
```

**Output:**

![image](https://github.com/user-attachments/assets/2567bdd2-b84a-464d-abd7-4e4bd9759d21)

**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/d3ef6a60-5ebc-4477-a6b1-59e11720fbc7)


```sql
--

SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;

```

**Output:**

![image](https://github.com/user-attachments/assets/d3346633-5f9e-4fc5-87c6-8245b5b38864)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/64c75b53-ce23-4ffc-a1af-bbaaca0a4630)


```sql
-- SELECT o.ord_no, o.purch_amt, o.ord_date, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.commission = (
  SELECT MAX(commission)
  FROM salesman
);

```

**Output:**

![image](https://github.com/user-attachments/assets/79b61c0d-8c73-4356-9670-bc911502081a)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/b77055f2-a53b-4c21-a47d-e5f771fe5635)


```sql
-- 
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

![image](https://github.com/user-attachments/assets/e98ed4f3-2c8c-4ead-a07d-ecdcf0e5a6de)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/f94b0cbf-4efb-4075-9838-93f9cdbbda4e)


```sql
--

SELECT department_id AS depar, department_name
FROM Departments
WHERE LENGTH(department_name) > (
  SELECT AVG(LENGTH(department_name))
  FROM Departments
);

```

**Output:**

![image](https://github.com/user-attachments/assets/63fb1530-906b-4275-a489-21d8890b4d24)


**Question 9**
---
--![image](https://github.com/user-attachments/assets/f0014c2b-db2f-4578-98c9-8adfefbebbd8)


```sql
--

SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/6bdfdfa5-9937-49c6-b565-c838d34ebf6a)


**Question 10**
---
--![image](https://github.com/user-attachments/assets/a67f11cb-306b-46f4-8560-9b83e4e7dcac)


```sql
-- 
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;

```

**Output:**

![image](https://github.com/user-attachments/assets/f751a3ed-3afb-4318-96a3-8abec6da9054)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
