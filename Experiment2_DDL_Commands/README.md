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
--
![image](https://github.com/user-attachments/assets/f4396372-b8ce-46ad-9abc-e43fb13ae25f)


```sql
---

CREATE TABLE Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE,
Amount REAL CHECK(Amount>0),
DueDate DATE CHECK(DueDate>InvoiceDate),
OrderID INTEGER,
FOREIGN KEY (OrderID)REFERENCES Orders(OrderID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/409d9ce5-fe23-4251-b4d3-8e8a660f9d65)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/55bad4d8-0e62-479c-b6cd-7175f52154e3)


```sql
--
INSERT INTO Employee(EmployeeID,Name,Position, Department,Salary)
values
(2,"John Smith","Developer","IT",75000),
(3,"Anna Bell","Designer","Marketing",68000);
```

**Output:**

![image](https://github.com/user-attachments/assets/9cead7cf-1627-4ab4-8077-110afb3d9ee8)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/9db85c6f-8a42-40e7-ae72-37a9002d6b46)

```sql
-- select * from Discontinued_products
union all
select * from Products
```

**Output:**

![image](https://github.com/user-attachments/assets/eefe1a64-e24d-4d9b-a323-74ff80c61cf4)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/f28c5fff-5832-42be-afde-611ec6128f46)


```sql
-- CREATE TABLE Products(
ProductID primary key,
ProductName NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK (Stock>=0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/8386e879-ef28-41c0-81e6-878d55b5dff6)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/8862c771-7438-480e-a590-9d858c8ee89b)

```sql
-- CREATE TABLE Products(
ProductID INTEGER primary key,
ProductName TEXT Unique NOT NULL,
Price REAL CHECK (Price>0),
StockQuantity INTEGER CHECK(StockQuantity>0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/e9a40edc-5054-452b-a69e-6c50b92ed215)

**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/ba165d46-aa97-44b5-ad5a-d708d28f42d5)


```sql
-- CREATE TABLE Employees(
EmployeeID INTEGER primary key,
FirstName INTEGER NOT NULL,
LastName INTEGER NOT NULL,
Email VARCHAR(60) UNIQUE,
Salary INTEGER CHECK(Salary>0),
DepartmentID INTEGER,
foreign key(DepartmentID)references Departments(DepartmentID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/f35533e3-62f6-4be4-828a-d2f7f31c3ef3)


**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/91fc3f60-9598-4a91-b9af-b03a135868fd)

```sql
-- CREATE TABLE Products(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER
);
```

**Output:**

![image](https://github.com/user-attachments/assets/43465794-2a30-467d-9c5c-a378dbcd42af)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/c79193ba-ee27-4d75-ae28-4ac5e3ae64da)


```sql
-- INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode)
values
(301,"Michael Jordan","123 Maple St","Chicago",60616)
```

**Output:**

![image](https://github.com/user-attachments/assets/033f31e9-3d55-4258-ba62-7b65b8d5ef37)

**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/b039f51c-abac-477d-a4dc-d563ac0b16c8)


```sql
-- 
ALTER TABLE employee
RENAME COLUMN id to employee_id;
```

**Output:**
![image](https://github.com/user-attachments/assets/17107842-5884-48b0-93b7-4ff2735803da)

**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/a20d3f6e-b6ed-4647-a322-2fafe20fac16)


```sql
-- ALTER TABLE Student_details
ADD COLUMN "Mobilenumber" number;
```

**Output:**
![image](https://github.com/user-attachments/assets/b1cac1ba-e129-4e7d-a61a-cab95726a106)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
