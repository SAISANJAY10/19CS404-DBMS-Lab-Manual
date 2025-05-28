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
## Submission:

SAI SANJAY R - 212223040178

#### Question 1

![image](https://github.com/user-attachments/assets/6f912c3e-1b4d-468a-b172-21be7ac9c87b)

```sql
CREATE TABLE Employees(
EmployeeID PRIMARY KEY,
FirstName NOT NULL,
LastName NOT NULL,
Email UNIQUE,
Salary DECIMAL CHECK(Salary > 0),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

#### Output:

![image](https://github.com/user-attachments/assets/5e636b6f-2202-4347-a4ab-c090a377cf98)


#### Question 2

![image](https://github.com/user-attachments/assets/339193be-11fd-4c18-acb0-8dd32d6ca907)



```sql
ALTER TABLE Student_details
ADD Date_of_birth Date;
```

#### Output:

![image](https://github.com/user-attachments/assets/c6c79e3b-1bb5-438d-9ee1-f23b9bee0500)


#### Question 3

![image](https://github.com/user-attachments/assets/a70e2ecc-e02f-4381-892c-e110a8fe615e)



```sql
CREATE TABLE jobs (
job_id INTEGER PRIMARY KEY,
job_title TEXT DEFAULT '',
min_salary INTEGER DEFAULT 8000,
max_salary INTEGER DEFAULT NULL
);
```

#### Output:
![image](https://github.com/user-attachments/assets/d6ba2aa2-ef9a-4cd9-8ad7-a5da31fe93d6)


#### Question 4

![image](https://github.com/user-attachments/assets/3292bba6-9149-4125-abff-11c4252863b2)


```sql
CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT
);
```

#### Output:
![image](https://github.com/user-attachments/assets/f0f7520e-d867-43b4-bcf5-f9f2bfed0ad5)


#### Question 5

![image](https://github.com/user-attachments/assets/794fc695-211f-4086-bfac-420d4edd92f8)

```sql
INSERT INTO Customers (CustomerID,  Name, Address, City, ZipCode)
VALUES (306, "Diana Prince",  "Themyscira", NULL, NULL);

INSERT INTO Customers (CustomerID,  Name, Address, City, ZipCode)
VALUES (307, "Bruce Wayne", "Wayne Manor", "Gotham", "10007");

INSERT INTO Customers (CustomerID,  Name, Address, City, ZipCode)
VALUES (308, "Peter Parker", "Queens", NULL, "11375");
```

#### Output:
![image](https://github.com/user-attachments/assets/9d743dc5-d165-479a-a1b2-939192defd4f)


#### Question 6

![image](https://github.com/user-attachments/assets/a4eb7aea-b69e-4681-8b1d-32a91af9fcdf)

```sql
ALTER TABLE books
ADD ISBN varchar(30);

ALTER TABLE books
ADD domain_dept varchar(30);
```

#### Output:

![image](https://github.com/user-attachments/assets/1d44a0a7-da08-4dcd-b09e-9c11c6cd270f)

#### Question 7

![image](https://github.com/user-attachments/assets/76b6ee0d-b96a-4209-82ea-8ab8d47358d6)

```sql
CREATE TABLE Shipments(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

#### Output:

![image](https://github.com/user-attachments/assets/0c1d592f-6e52-48f7-8de3-cf8a00b9cf8d)

#### Question 8

![image](https://github.com/user-attachments/assets/7cb8dfe7-a2cf-407a-b4ab-b911e0db5a94)

```sql
INSERT INTO Student_details(RollNo, Name, Gender, Subject, MARKS)
SELECT RollNo, Name, Gender,Subject, MARKS FROM Archived_students;
```

#### Output:

![image](https://github.com/user-attachments/assets/c1f571b6-2045-45df-8bf9-cc99c9e9084f)

#### Question 9

![image](https://github.com/user-attachments/assets/8d006093-0e18-4eb3-8b8f-bcb1748a4df9)

```sql
INSERT INTO Books(ISBN, Title, Author, Publisher, Year)
VALUES ("978-1234567890", "Data Science Essentials", "Jane Doe", "TechBooks", 2024);
```

#### Output:

![image](https://github.com/user-attachments/assets/0abadfe5-293f-4e9e-a02e-88e09dcbcbf8)

#### Question 10

![image](https://github.com/user-attachments/assets/5b0bfafa-b1da-4b3e-aee2-51833ef0ca56)

```sql
CREATE TABLE orders(
ord_id TEXT NOT NULL CHECK(LENGTH(ord_id)=4),
item_id TEXT NOT NULL,
ord_date DATE,
ord_qty INTEGER,
cost INTEGER,
PRIMARY KEY (item_id, ord_date)
);
```

#### Output:

![image](https://github.com/user-attachments/assets/c5d597ef-d573-4a65-8c1d-acfb0c9cba3e)

## Module - 1 Grade :

![image](https://github.com/user-attachments/assets/2aca74b1-1bb4-4785-839b-d741835d37d7)

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
