# 🟦 **SQL Basics (Module 2)**

*Learn how to create tables, insert data, fetch information, update records, and delete entries — the foundation of all SQL work.*

---

# 🧭 **Module Overview**

In this module, you will learn:

* 🆚 **SQL vs MySQL**
* 📊 **Data Types in MySQL**
* 🏷️ **CREATE DATABASE & TABLE**
* ➕ **INSERT Rows**
* 📤 **SELECT Data**
* ✏️ **UPDATE Rows**
* ❌ **DELETE Rows**
* 🌱 Bonus: **NULL handling & Aliases**

All topics include examples, exercises, and mini-assignments.

---

# 🆚 **2.1 SQL vs MySQL**

### 🧠 SQL (Structured Query Language)

A language used to **query and manipulate** relational databases.

### 🐬 MySQL

A **database server** that uses SQL to manage data.

### 📌 Analogy

**SQL = English language**
**MySQL = A person who understands English**

---

# 📊 **2.2 MySQL Data Types (Beginner Essentials)**

### 🔢 Numeric Types

* `INT` — whole numbers
* `DECIMAL(10,2)` — money, precise values
* `FLOAT`, `DOUBLE` — scientific values

### 🔤 String Types

* `VARCHAR(100)` — names, emails
* `CHAR(10)` — fixed length
* `TEXT` — long paragraphs

### 🕒 Date & Time Types

* `DATE`
* `TIME`
* `DATETIME`
* `TIMESTAMP`

### 📌 Example

```sql
CREATE TABLE employees (
  id INT,
  name VARCHAR(50),
  salary DECIMAL(10,2),
  joining_date DATE
);
```

---

# 🏷️ **2.3 CREATE Database & Table**

### 📁 Create a Database

```sql
CREATE DATABASE company;
```

### 📂 Use the Database

```sql
USE company;
```

### 📄 Create a Table

```sql
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  role VARCHAR(50),
  salary DECIMAL(10,2),
  join_date DATE
);
```

---

# ➕ **2.4 INSERT — Adding Rows**

### 🧠 Syntax

```sql
INSERT INTO table_name (col1, col2, ...) 
VALUES (value1, value2, ...);
```

### ⭐ Example

```sql
INSERT INTO employees (id, name, role, salary, join_date)
VALUES (1, 'John Doe', 'Manager', 65000.00, '2021-01-15');
```

---

# 📤 **2.5 SELECT — Retrieving Data**

### 🧠 Basic SELECT

```sql
SELECT * FROM employees;
```

### 🎯 Select Specific Columns

```sql
SELECT name, salary FROM employees;
```

---

# ✏️ **2.9 UPDATE — Modify Existing Rows**

### 🧠 Syntax

```sql
UPDATE table_name
SET column = value;
```

### ⭐ Example

```sql
UPDATE employees
SET salary = 70000;
```
---

# ❌ **2.10 DELETE — Remove Rows**

### 🧠 Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### ⭐ Example

```sql
DELETE FROM employees
WHERE id = 3;
```

⚠️ Never run:

```sql
DELETE FROM employees;
```

unless you want to delete **EVERY** record.

---

# 🌱 Bonus Topics

## 🔸 Handling NULL

```sql
SELECT * FROM employees
WHERE salary IS NULL;
```

## 🔸 Aliases (Temporary Names)

```sql
SELECT salary * 12 AS annual_salary
FROM employees;
```

---

# 📝 **Practice Exercises**

### 🏋️ Exercise 1 — Create Table

Create a table **products** with:

* product_id
* name
* price
* category

---

### 🏋️ Exercise 2 — Insert Data

Insert **5 sample products**.

---

### 🏋️ Exercise 3 — Queries

Write queries for:

1. Products with price > 500
2. Products in category "Electronics"
3. Top 2 expensive products
4. Products with price between 100 and 500

---

# 🧱 **Mini Project — Employee Database**

Create a database **office_db** with table **staff**:

Columns:

* staff_id
* name
* department
* salary
* hire_date

### Then write:

* All employees in “HR”
* Employees earning above 60,000
* Raise salary by 10% for IT employees
* Delete employees hired before 2019

---

# 🎓 **End-of-Module Assignment (Graded)**

Build a complete **Student Information System**.

### Tables:

* students
* courses
* enrollments

### Required Queries:

1. List all students
2. Students enrolled in “Computer Science”
3. Highest-scoring students (using a marks column)
4. Increase marks of all students by 5%

---

# 🎉 **End of Module 2**

You now understand:

✔ CRUD operations
✔ Basic SQL syntax
✔ Filtering, sorting, and limiting
✔ Beginner-level data manipulation
✔ Real-world database usage

---

If you want the next module, say:

👉 **Generate Module 3 (Joins & Advanced SELECT)**
