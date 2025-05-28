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
## Submission:

#### SAI SANJAY - 212223040178

**Question 1**
--
![Screenshot 2025-04-30 201427](https://github.com/user-attachments/assets/63bb895f-f794-4489-9ba2-6609ce2893e1)

```sql
select Medication , AVG(Dosage) as AvgDosage from Prescriptions group by Medication;
```

**Output:**

![Screenshot 2025-04-30 201506](https://github.com/user-attachments/assets/3914beea-af6d-434e-abd5-39cba43e3852)

**Question 2**
---
![Screenshot 2025-04-30 201525](https://github.com/user-attachments/assets/b294f15f-d6dd-429c-bd85-c2c8ac6553cb)

```sql
select Specialty , Gender , count(*) as TotalDoctors from Doctors group by Specialty,Gender;
```

**Output:**

![Screenshot 2025-04-30 201558](https://github.com/user-attachments/assets/bc7ec63d-1aba-468d-b28c-41ab8ce985e3)

**Question 3**
---
![Screenshot 2025-04-30 201621](https://github.com/user-attachments/assets/626c8355-934b-4974-a981-7ff7f0e61160)

```sql
select DoctorId , count(*) as TotalPrescriptions from Prescriptions group by DoctorId;
```

**Output:**

![Screenshot 2025-04-30 201649](https://github.com/user-attachments/assets/522e7cd4-deab-45f5-9e75-dc9990792849)

**Question 4**
---
![Screenshot 2025-04-30 201718](https://github.com/user-attachments/assets/d5a9c13d-d941-4bbb-a202-14731ec27a09)

```sql
select avg(length(name)) as avg_name_length from customer where city = 'Chennai';
```

**Output:**

![Screenshot 2025-04-30 201816](https://github.com/user-attachments/assets/d13b4ade-23d6-4c0b-b58f-909068577885)

**Question 5**
---
![Screenshot 2025-04-30 201837](https://github.com/user-attachments/assets/8640c50c-7c5b-4aaf-9048-e0168ff7b532)

```sql
select Min(purch_amt) as MINIMUM from orders ;
```

**Output:**

![Screenshot 2025-04-30 201909](https://github.com/user-attachments/assets/b5d996d9-1793-42e4-b164-c1e84d67f16c)

**Question 6**
---
![Screenshot 2025-04-30 201930](https://github.com/user-attachments/assets/fcc13aca-4388-4b05-a517-9772a8b484e2)

```sql
select count(*) as employees_count from employee where income > 50000;
```

**Output:**

![Screenshot 2025-04-30 202005](https://github.com/user-attachments/assets/83df890c-b3a4-4150-9d49-3f9f8736767d)

**Question 7**
---
![Screenshot 2025-04-30 202028](https://github.com/user-attachments/assets/f8d7d772-b44d-4c36-a868-2cd93c595bd9)

```sql
select avg(length(email)) as avg_email_length from customer ;
```

**Output:**

![Screenshot 2025-04-30 202114](https://github.com/user-attachments/assets/5d84c227-3d80-464c-83d6-311ca6d08bde)

**Question 8**
---
![Screenshot 2025-04-30 202142](https://github.com/user-attachments/assets/9418b04e-335b-431c-b6b3-c3abd8720586)

```sql
select occupation , MIN(workhour) from employee1  group by occupation having MIN(workhour) > 8;
```

**Output:**

![Screenshot 2025-04-30 202232](https://github.com/user-attachments/assets/d1ff51a8-cccf-463b-b160-9b48da155e0e)

**Question 9**
---
![Screenshot 2025-04-30 202254](https://github.com/user-attachments/assets/75aac6c3-3b7f-4d62-bcc0-cfc532590357)

```sql
select (age/5)*5 as age_group, MIN(salary) from customer1 group by (age/5)*5 having MIN(salary) < 2000;
```

**Output:**

![Screenshot 2025-04-30 202328](https://github.com/user-attachments/assets/0372bbdd-e558-4eaa-8b5e-026b8bb759df)

**Question 10**
---
![Screenshot 2025-04-30 202357](https://github.com/user-attachments/assets/b5f870e6-5304-46b6-bb91-05f9cedcc95f)

```sql
select (age/5)*5 as age_group , MIN(age) from customer1 group by (age/5)*5 having MIN(age) <25;
```

**Output:**

![Screenshot 2025-04-30 202435](https://github.com/user-attachments/assets/8164754d-aed5-4a0c-bda7-5114cfff472b)

## Module-3 Grade:

![Screenshot 2025-04-30 202520](https://github.com/user-attachments/assets/fe0bb5f7-35ae-4297-b69d-9f51c28df6a9)

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
