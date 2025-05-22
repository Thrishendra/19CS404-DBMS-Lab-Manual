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
--
-- ![image](https://github.com/user-attachments/assets/c8b25e49-bc19-4b1b-9591-268a569d836e)


```sql
-- select
SUBSTR(Email, INSTR(Email,'@')+1) AS EmailDomain,
COUNT(*) AS TotalPatients
FROM
Patients
GROUP BY
EmailDomain;
```

**Output:**

![image](https://github.com/user-attachments/assets/f443e432-9d9d-47b0-8441-feb589288b9e)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/4b6f967d-90ad-4da8-a2ea-6384df795a48)


```sql
-- 
SELECT 
  DATE(AppointmentDateTime) AS AppointmentDate, 
  COUNT(AppointmentID) AS TotalAppointments
FROM 
  Appointments
GROUP BY 
  DATE(AppointmentDateTime);
```

**Output:**

![image](https://github.com/user-attachments/assets/f668ee0f-3b91-45ed-bd06-5881055f39fc)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/f65eddb0-360a-458e-a652-e2474e4392ac)


```sql
-- select
Specialty,
COUNT(*) AS TotalDoctors
FROM
Doctors
GROUP BY
Specialty;
```

**Output:**

![image](https://github.com/user-attachments/assets/6879aacd-9e97-457e-ae2c-6910867eb8d9)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/de0f197e-0eae-4689-a998-d444b6099ce8)

```sql
-- select
COUNT(*) AS employees_count
FROM
employee
WHERE
income>50000;
```

**Output:**

![image](https://github.com/user-attachments/assets/ee75ed8f-5aba-4367-a52f-b46bd5447c05)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/0adcb46a-4cd1-46c8-bbd8-ef4ffb0fd329)

```sql
-- SELECT
SUM(inventory) AS total
FROM
fruits
WHERE
unit = 'LB';
```

**Output:**

![image](https://github.com/user-attachments/assets/4ee4dd32-25d4-4223-8750-152d75ee423a)

**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/269d0a7a-d805-451d-8bc1-c5a857af3154)

```sql
-- SELECT
sum(income) AS total_income
FROM
employee
WHERE
age>=40;
```

**Output:**

![image](https://github.com/user-attachments/assets/0007df8d-08b7-4f2a-b3d8-d7c83541a805)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/ab50d0f9-c1d3-4b9c-997f-6c293730958e)


```sql
-- SELECT
AVG(income) AS avg_income
FROM
employee
WHERE
name LIKE 'A%';
```

**Output:**

![image](https://github.com/user-attachments/assets/afb11255-7a16-459d-aead-0cd84dfe0fd4)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/fc1e292f-123b-483a-b04c-6e0f60cdfef5)


```sql
-- SELECT category_id, product_name, Price as Price
FROM products
WHERE (category_id, Price) IN (
    SELECT category_id, MAX(Price)
    FROM products
    GROUP BY category_id
    HAVING MAX(Price) > 15
);

```

**Output:**

![image](https://github.com/user-attachments/assets/07286eb0-0cce-46ed-a5cc-fe5cc1c46c9a)

**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/8eb580b6-703a-4c15-8a4c-6cfef6d5d7ea)


```sql
-- 
SELECT age, MIN(income) 
FROM employee 
GROUP BY age 
HAVING MIN(income) < 400000;
```

**Output:**

![image](https://github.com/user-attachments/assets/313a8d26-22af-4aca-8ba4-3a3641fcec80)

**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/69f73a71-c4d4-451a-91d7-bdadb42d8311)

```sql
-- 
SELECT category_id, count(product_name)
FROM products
GROUP BY category_id
HAVING category_id < 3;

```

**Output:**

![image](https://github.com/user-attachments/assets/aa449b18-dfe3-403b-9f4e-7d34e5fc88fd)

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
