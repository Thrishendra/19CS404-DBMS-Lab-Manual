# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/24b299e3-f43b-4617-92d1-ba95e561dcac)


```sql
-- UPDATE products SET reorder_lvl=reorder_lvl*0.7 WHERE product_name LIKE "%cream%" AND quantity>reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/94ccce41-f7ce-4d3d-b586-8eec348d5471)


**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/be8d4773-d20f-4cf1-bbfa-9e46b00efbd6)

```sql
-- UPDATE customer SET grade=5 WHERE city="Chennai";
```

**Output:**

![image](https://github.com/user-attachments/assets/477d05a9-fa26-45a6-8f99-064d1c15576b)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/e9ed7aac-1e98-4ac3-9488-51c4d1f495fb)


```sql
-- UPDATE employees SET email="Unavailable";
```

**Output:**

![image](https://github.com/user-attachments/assets/fef0c609-251a-40f3-8892-7810f4bf4e6a)

**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/943f7cc1-d5f1-4724-a798-7fe37a52599c)


```sql
-- UPDATE products SET sell_price=sell_price*1.15 WHERE quantity<50 AND supplier_id=10;![Uploading image.png…]()

```

**Output:**

![image](https://github.com/user-attachments/assets/089efe1e-5575-4427-9bc7-8a88ffa666e4)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/cefecbf1-b9bd-435a-84a1-268ad169deae)

```sql
-- UPDATE sales SET total_sell_price=quantity*sell_price WHERE product_id=10;

```

**Output:**

![image](https://github.com/user-attachments/assets/fa43075c-2b04-45f8-820b-36d2030a26b3)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/dbd057b7-589d-425c-8bfb-3923a0d45f9b)

```sql
-- DELETE FROM customer WHERE GRADE>=2;
```

**Output:**

![image](https://github.com/user-attachments/assets/6b1c746a-8edc-460b-9644-59ba09bd0a94)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/a57d91fd-bc9a-4c89-ba3f-aabfa17a963f)

```sql
-- DELETE FROM customer WHERE cust_country="India" AND cust_city!="Chennai";
```

**Output:**

![image](https://github.com/user-attachments/assets/7cc8214e-0dc4-4f0b-900c-3f8f1407af5b)

**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/a60de25f-7d27-4fe8-94ff-0be81f20be54)


```sql
-- DELETE FROM customer WHERE cust_city!="New York" AND outstanding_amt>5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/0c76b9f9-3831-4cba-bde7-08b38a75f663)


**Question 9**
---
--![image](https://github.com/user-attachments/assets/2a410e25-012d-4541-b54e-cc4a63abf3ac)

```sql
-- DELETE FROM Customer WHERE cust_country="UK" AND working_area="London" AND grade<3;
```

**Output:**

![image](https://github.com/user-attachments/assets/5f38d196-fe4e-426b-847c-cd8dfffb0c66)

**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/3aee313a-43c9-441a-9378-9c9c8a48ad4f)


```sql
-- delete from customer where grade%2!=0;
```

**Output:**

![image](https://github.com/user-attachments/assets/8e72c9f9-794a-4c55-9378-0a02231e3b37)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
