# Experiment 6: Joins
REG NO: 212223100006
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

**Question 1**
--
![Screenshot 2025-05-02 192729](https://github.com/user-attachments/assets/9662554a-6d88-452d-af16-10ab72298089)


```sql
   SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
LEFT JOIN 
    salesman s ON o.salesman_id = s.salesman_id
```

**Output:**

![Screenshot 2025-05-02 193123](https://github.com/user-attachments/assets/ace00ac8-7c00-46d6-b277-9d4af3386aa7)


**Question 2**
---
![Screenshot 2025-05-02 192740](https://github.com/user-attachments/assets/93ec0bce-0592-4461-bc33-02d1493ae097)


```sql
SELECT
    p.date_of_birth,
    a.*
FROM
    patients p
INNER JOIN
    appointments a ON p.patient_id = a.patient_id
WHERE
    p.first_name = 'Alice';

```

**Output:**

![Screenshot 2025-05-02 193133](https://github.com/user-attachments/assets/1d9704cd-2f7a-4b6c-94ef-275da32f4500)


**Question 3**
---
![Screenshot 2025-05-02 192753](https://github.com/user-attachments/assets/010cfb4f-79f5-4f98-9b3e-fe392d526b17)


```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM
    customer c
JOIN
    salesman s ON c.salesman_id = s.salesman_id
WHERE
    s.commission > 0.12;

```

**Output:**

![Screenshot 2025-05-02 193141](https://github.com/user-attachments/assets/f14f55a3-738a-412d-ae3d-89df06d54f80)


**Question 4**
---
![Screenshot 2025-05-02 192801](https://github.com/user-attachments/assets/3cdb9ac4-df01-4947-85a4-1f6da11da91a)


```sql
SELECT
    p.*
FROM
    patients p
INNER JOIN
    appointments a ON p.patient_id = a.patient_id
WHERE
    a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

![Screenshot 2025-05-02 193150](https://github.com/user-attachments/assets/d6e158e3-3865-431f-bdff-af5b75d5f7cf)



**Question 5**
---
![Screenshot 2025-05-02 192815](https://github.com/user-attachments/assets/5d9ddc18-efe7-4673-9326-6fa6bd149a3a)


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

![Screenshot 2025-05-02 193159](https://github.com/user-attachments/assets/c0eed26b-7eb1-4394-b67e-5568d6253622)


**Question 6**
---
![Screenshot 2025-05-02 192827](https://github.com/user-attachments/assets/84884d90-bcd7-4fcb-860a-4a35f031db42)


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
INNER JOIN 
    customer c ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![Screenshot 2025-05-02 193217](https://github.com/user-attachments/assets/1033a86b-3d1e-4c79-8f4a-f6b4371c1cca)


**Question 7**
---
![Screenshot 2025-05-02 192838](https://github.com/user-attachments/assets/7a1b9603-4c1c-4a98-ad6f-fe94a375b744)


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.purch_amt > 1000;

```

**Output:**

![Screenshot 2025-05-02 193225](https://github.com/user-attachments/assets/d82f50cb-d39a-4f85-9214-de4cc8861ce7)


**Question 8**
---
![Screenshot 2025-05-02 192847](https://github.com/user-attachments/assets/03739ccf-cf4a-4728-b6a1-b49863452b24)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

![Screenshot 2025-05-02 193234](https://github.com/user-attachments/assets/bbf53faa-1618-4f32-9787-b5eb8499e86f)


**Question 9**
---
![Screenshot 2025-05-02 192856](https://github.com/user-attachments/assets/f84cff89-f5fe-43ff-9e46-08bfe4f55fff)


```sql
SELECT 
    p.first_name AS patient_name,
    t.test_name
FROM 
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/d9b0a4a2-a109-43af-8a4b-ec18bc654353)



**Question 10**
---
![Screenshot 2025-05-02 192903](https://github.com/user-attachments/assets/7e8b0142-f35b-49c2-acb8-26376330a4b3)


```sql
SELECT 
    s.name,
    c.cust_name,
    c.city,
    c.grade,
    c.salesman_id
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id
WHERE 
    c.grade <= 100;

```

**Output:**

![Screenshot 2025-05-02 193249](https://github.com/user-attachments/assets/772bacac-64e7-4dbf-9a56-08649bff8477)


![Screenshot 2025-05-02 193306](https://github.com/user-attachments/assets/256342e8-70ce-409b-a09d-4c0699394667)

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
