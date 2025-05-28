# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```
#### SUBMISSION

SAI SANJAY R - 212223040178

**Question 1**
--
![Screenshot 2025-05-03 115259](https://github.com/user-attachments/assets/8398610f-fd62-45cc-94a4-248b47a69468)

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/6b57727a-4733-4907-a086-8ad26a6210dd)

**Question 2**
---
![image](https://github.com/user-attachments/assets/a3b6d85d-4972-471d-8c37-4b8599ab2925)

```sql
SELECT 
    c.cust_name,
    s.commission
FROM 
    customer c
LEFT JOIN 
    salesman s ON c.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/65122ce3-e41c-4654-88dd-8e46a3dd70cc)

**Question 3**
---
![image](https://github.com/user-attachments/assets/9d42b1cb-0ae1-45ea-8499-bc67bcfdf785)

```sql
SELECT 
    p.first_name,
    s.*
FROM 
    patients p
INNER JOIN 
    surgeries s ON p.patient_id = s.patient_id
WHERE 
    p.date_of_birth > '1990-01-01';
```

**Output:**

![image](https://github.com/user-attachments/assets/4070162c-ffa4-46bc-818d-125405f6784f)

**Question 4**
---
![image](https://github.com/user-attachments/assets/097ac2df-639e-4f9a-b63b-5bb4857ca6e9)

```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/b955516a-4a9c-4d8f-a5b6-ac47fdacae63)

**Question 5**
---
![image](https://github.com/user-attachments/assets/0adb7085-5670-4066-a045-aced59785bfd)

```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/b2f7faf5-22a5-4a5e-adac-92e2f792b694)

**Question 6**
---
![image](https://github.com/user-attachments/assets/b7d17e37-bbb4-4f00-b7a2-8387c96ac365)

```sql
SELECT 
    s.name AS Salesman,
    c.cust_name AS cust_name,
    s.city
FROM 
    salesman s
JOIN 
    customer c ON s.city = c.city;
```

**Output:**

![image](https://github.com/user-attachments/assets/1ad6a5d7-551d-4488-94ec-aff5da67d6f6)

**Question 7**
---
![image](https://github.com/user-attachments/assets/31ca45d7-7c78-430e-9969-648f88737bab)

```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM 
    patients p
INNER JOIN 
    doctors d ON p.doctor_id = d.doctor_id
WHERE 
    p.discharge_date IS NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/4f612d0f-4cfc-464e-a5fd-f554f0ca7ebb)

**Question 8**
---
![image](https://github.com/user-attachments/assets/3805d112-16db-475e-81dd-39f3da1243e9)

```sql
SELECT 
    t.*
FROM 
    test_results t
INNER JOIN 
    patients p ON t.patient_id = p.patient_id
WHERE 
    p.first_name = 'Alice';
```

**Output:**

![image](https://github.com/user-attachments/assets/023d6bc0-d983-4952-908c-6f841fe7d9a1)

**Question 9**
---
![image](https://github.com/user-attachments/assets/f8357338-9f0c-47d7-a1e1-1c526a0ea990)

```sql
SELECT 
    c.*
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';
```

**Output:**

![image](https://github.com/user-attachments/assets/9e695eb1-99b0-4f63-927b-2a61c6d0b265)

**Question 10**
---
![image](https://github.com/user-attachments/assets/968f400b-1d26-414c-a19c-34c2b8bd97e2)

```sql
SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;
```

**Output:**

![image](https://github.com/user-attachments/assets/8ad874f0-6185-4527-aca7-9d5bfbd64f98)


## Module - 5 Grade :

![image](https://github.com/user-attachments/assets/d831bc83-4ae3-4b1b-9824-a65c6e4bf2bb)

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
