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
 ![image](https://github.com/user-attachments/assets/08609076-2114-46e6-b8c9-3ad33d1592b0)


```sql
insert into Products(Name,Category,price,Stock)
values("Smartphone","Electronics",800,150),
("Headphones","Accessories",200,300);
```

**Output:**

![image](https://github.com/user-attachments/assets/2e7e0ae0-30c9-45df-8198-a3313745d10a)


**Question 2**
---
![image](https://github.com/user-attachments/assets/61a5bc37-5de5-4880-8412-ea3d1d089606)


```sql
 create table item(
item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),foreign key(icom_id)
references company(com_id) on update set null on delete set null);
```

**Output:**

![image](https://github.com/user-attachments/assets/7d88dead-fb07-43a0-90e7-751387988bb0)


**Question 3**
---
![image](https://github.com/user-attachments/assets/9b053a92-9a28-4966-ade7-abf71aea4fb6)


```sql
create table Department(
DepartmentID int primary key,
DepartmentName varchar(50) UNIQUE NOT NULL,
Location varchar(100));
```

**Output:**
![image](https://github.com/user-attachments/assets/a0c8ed3a-5f6d-4d23-93b7-5004511fa34c)


**Question 4**
---
![image](https://github.com/user-attachments/assets/07be1b8c-e7cd-4db6-8a20-3b33c40c1b49)


```sql
create table jobs(
job_id int,
job_title varchar(50) default "",
min_salary int default 8000,max_salary int);
```

**Output:**
![image](https://github.com/user-attachments/assets/76d6e18e-64f1-4770-a6cc-d6e27536921f)


**Question 5**
---
![image](https://github.com/user-attachments/assets/ffbce42d-a9b4-4350-8316-5f87a6d93a1c)


```sql
alter table Employees add column Date_of_joi Date;
alter table employees rename column job_title to Designation;
```

**Output:**

![image](https://github.com/user-attachments/assets/31d91fbb-7442-4a8b-ad2f-d1757e7dd2b6)


**Question 6**
---
![image](https://github.com/user-attachments/assets/7c2f8392-cedc-49ae-8959-820f84510686)

```sql
insert into Products(ProductID,ProductName,Price,Stock)
select ProductID,ProductName,Price,Stock from Discontinued_products;
```

**Output:**

![image](https://github.com/user-attachments/assets/478bd1b6-7571-405b-a8bd-f36eb48a9383)


**Question 7**
---
![image](https://github.com/user-attachments/assets/cd2b2baf-98c8-4bf1-b749-711c2fee4283)


```sql
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
```

**Output:**

![image](https://github.com/user-attachments/assets/f37a1741-8bfc-4e7e-a85f-705f1b7f500f)


**Question 8**
---
![image](https://github.com/user-attachments/assets/cd2040eb-0f7d-481c-acf6-7aaf229155b6)


```sql
create table item(item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),
foreign key(icom_id) references company(com_id) on update cascade on delete cascade);
```

**Output:**
![image](https://github.com/user-attachments/assets/04e77140-e6ec-40fd-a2a9-a78341622bf3)


**Question 9**
---
![image](https://github.com/user-attachments/assets/a35ceb4e-f8fe-44d4-bead-eadb15964eb4)


```sql
insert into Student_details(RollNo,Name,Gender) values(204,"Samuel Black","M");
```

**Output:**

![image](https://github.com/user-attachments/assets/cbc5828c-e6da-401d-b525-859f24003008)


**Question 10**
---
![image](https://github.com/user-attachments/assets/93d08baf-6d40-4f4c-83ab-cdc39a9e11a2)


```sql
create table Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

![image](https://github.com/user-attachments/assets/75324efd-adab-4ead-bed8-2ce4da36998b)

## GRADES:

![image](https://github.com/user-attachments/assets/12ee4a0a-f8d5-4063-aa3e-6579e529558c)

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
