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
![image](https://github.com/user-attachments/assets/27bd2cd1-855f-4b4f-99a2-c5adb0c958b9)


```sql
UPDATE suppliers set supplier_name=UPPER(supplier_name) where contact_person like '%Singh%';
```

**Output:**
![image](https://github.com/user-attachments/assets/92fccbd0-7733-4b83-80ad-2aaf89a18419)


**Question 2**
---
![image](https://github.com/user-attachments/assets/378cb935-145e-43b6-97ea-baf8e9780dd5)


```sql
update suppliers set supplier_name="A1 Suppliers" where supplier_id=8;
```

**Output:**

![image](https://github.com/user-attachments/assets/399239fd-6458-4b96-a44f-c31e77501fa6)


**Question 3**
---
![image](https://github.com/user-attachments/assets/f896aea0-c243-4767-8e68-f4fdea4ab6fd)


```sql
update sales set sell_price=sell_price+0.05*sell_price where sale_date='2023-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/28dfc2e9-be4e-4255-b3bf-8307c4772fc0)


**Question 4**
---
![image](https://github.com/user-attachments/assets/7ee5079b-8001-401d-aa54-8c94ce677255)


```sql
delete from Customer  where WORKING_AREA is 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/311bfeea-ff3e-4e91-9318-3f1a4835033c)


**Question 5**
---


```sql
delete from Customer
where (GRADE>2 and PAYMENT_AMT<(select AVG(PAYMENT_AMT) from customer))
 OR OUTSTANDING_AMT>8000;
```

**Output:**

![image](https://github.com/user-attachments/assets/916f9d2d-f3a0-4146-8cd7-fcd9f774d12a)

**Question 6**
---
![image](https://github.com/user-attachments/assets/3356fa63-34c5-413d-86a0-5db8fb637e7d)


```sql
delete from customer where grade<2;
```

**Output:**

![image](https://github.com/user-attachments/assets/d2c3a1da-d08d-4088-aed4-1d18ef7b2446)


**Question 7**
---
![image](https://github.com/user-attachments/assets/c74fffe7-eb38-438d-935e-ffe731a84fb3)


```sql
select categoryName,description from categories order by categoryName;
```

**Output:**

![image](https://github.com/user-attachments/assets/9d0408e2-4733-4113-8aac-f5162bd9ca03)


**Question 8**
---
![image](https://github.com/user-attachments/assets/5ed3ce37-7413-4041-9d82-11770e9bf32e)

```sql
select id,value1,
CASE
WHEN value1>0 THEN 'Positive'
WHEN value1<0 then 'Negative'
Else 'Zero'
END AS value_status
FROM Calculations;
```

**Output:**

![image](https://github.com/user-attachments/assets/a9e1960e-5dd3-4825-a2d4-160332077c05)


**Question 9**
---
![image](https://github.com/user-attachments/assets/3db39298-1d08-4d7e-9af8-de4c19633161)


```sql
select customer_id,cust_name,city,grade,salesman_id from customer
where city="New York" or grade>200;
```

**Output:**
![image](https://github.com/user-attachments/assets/0fa837f8-d9ac-4353-b4ee-6bc47ff20f55)


**Question 10**
---
-![image](https://github.com/user-attachments/assets/96d6137e-0f3c-4ef7-a05a-18596e8116ad)

```sql
select product_id,original_price,discount_percentage,
original_price-original_price*discount_percentage as discounted_price
from Products;
```

**Output:**

![image](https://github.com/user-attachments/assets/b9ceb64c-ffad-49bd-99ca-e81c2c18ef7f)

## GRADES:
![image](https://github.com/user-attachments/assets/ae28d673-7714-4b7b-b525-e498ecc33e52)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
