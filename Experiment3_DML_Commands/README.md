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

### Submission:

### SAI SANJAY R - 212223040178 

#### Question 1

![image](https://github.com/user-attachments/assets/b121fb43-3052-40f7-9940-f57a79a0d543)

```sql
update products
set reorder_lvl = reorder_lvl*1.3
where category = 'Food' and quantity <50;
```

#### Output: 

![image](https://github.com/user-attachments/assets/41ef7d07-1397-4e1b-8e14-183447c07c67)

#### Question 2

![image](https://github.com/user-attachments/assets/c9466076-c4cb-4f53-adc3-018edbda9d22)

```sql
update Products 
set sell_price = cast(cost_price * 1.35 as int)
where ((sell_price-cost_price)/sell_price) <0.30;
```

#### Output: 

![image](https://github.com/user-attachments/assets/3478ee37-5aa2-4be6-acaa-0c4fca2dac0f)

#### Question 3

![image](https://github.com/user-attachments/assets/6f033971-e9ea-42ae-a8fa-19a74be192b4)

```sql
update Customer
set grade = 5 where city='Chennai';
```

#### Output: 

![image](https://github.com/user-attachments/assets/87bdf22f-b545-4373-a7d3-0fce68e0b1ab)

#### Question 4

![image](https://github.com/user-attachments/assets/056e4806-ac7d-4dec-8422-768fc7589189)

```sql
update suppliers
set supplier_name = upper(supplier_name)
where contact_person LIKE '%Singh%'
```

#### Output: 

![image](https://github.com/user-attachments/assets/c1119c9b-11c3-48ea-bd74-992c5b288389)

#### Question 5

![image](https://github.com/user-attachments/assets/c26f5f2b-9321-4ff4-bb20-201089980356)

```sql
update Products
set sell_price = sell_price *1.10
where category = 'Bakery';
```

#### Output: 

![image](https://github.com/user-attachments/assets/b467e396-b60a-425f-a641-6fc8dbf6056b)

#### Question 6

![image](https://github.com/user-attachments/assets/f5dfc680-7c1b-47d7-90d4-1d6a4569f1db)

```sql
delete from Doctors where specialization is NULL;
```

#### Output: 

![image](https://github.com/user-attachments/assets/4cd0a81b-3d80-4637-abab-2de34e65b855)

#### Question 7

![image](https://github.com/user-attachments/assets/db1e5c54-e8f3-40fa-bbc5-6eb9a4093034)

```sql
delete from Doctors where specialization = 'Cardiology';
```

#### Output: 

![image](https://github.com/user-attachments/assets/a8b3284e-f2fb-499f-87fe-e65e1e7548b8)

#### Question 8

![image](https://github.com/user-attachments/assets/18bee4af-2897-4256-b0bd-602982a4c649)

```sql
delete from Surgeries where surgery_id = 3;
```

#### Output: 

![image](https://github.com/user-attachments/assets/3ab7f0a5-4f9d-490a-990d-902a7c32b563)

#### Question 9

![image](https://github.com/user-attachments/assets/0a7d2886-c35f-43cc-a60a-127ced6db137)

```sql
delete from Customer where cust_country = 'India' and 
 cust_city != 'Chennai';
```

#### Output: 

![image](https://github.com/user-attachments/assets/1aed4662-5519-4ef8-ade9-302a0ea4e0bf)

#### Question 10

![image](https://github.com/user-attachments/assets/7ccfadb5-3df9-43e3-b83b-1690e71d807f)

```sql
delete from Customer where GRADE = 2 AND CUST_NAME LIKE 'M%'
AND PAYMENT_AMT <3000;
```

#### Output: 

![image](https://github.com/user-attachments/assets/52bb6307-d7f1-40cf-b5c4-3ddcd43161da)

## Module - 2 Grade:

![image](https://github.com/user-attachments/assets/dd1ef008-b6b0-4e15-9b37-5b52a36eb413)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
