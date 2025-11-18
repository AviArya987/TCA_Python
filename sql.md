# 🐬 **MySQL Syllabus for Data Science** 
---
## <img src="https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-6a5acd?style=for-the-badge" />

# 🗂️ **Module 1 — Database & MySQL Fundamentals**

### <img src="https://img.shields.io/badge/Progress-0%25-grey?style=flat-square"/>

### 📌 **Topics**

* 🧠 What is a database? Why SQL for Data Science?
* 📁 Types of databases (Relational vs NoSQL)
* 🐬 Installing & connecting MySQL (Workbench / CLI)
* 🏗️ Databases, Tables, Rows, Columns
* 🔑 Primary Keys, Foreign Keys (Basic intro)

---

### 🧩 **ASCII Diagram: How Data Lives in MySQL**

```
DATABASE
 └── employees
        ├── id (PK)
        ├── name
        ├── age
        ├── salary
        └── department_id → FK → departments.id
```
---

# 🟦 **Module 2 — SQL Basics (CRUD)**

### <img src="https://img.shields.io/badge/Progress-10%25-blue?style=flat-square"/>

### 📌 **Topics**

* 🏷️ CREATE database/table
* ➕ INSERT rows
* 📤 SELECT data
* ✏️ UPDATE rows
* ❌ DELETE rows

### 🔍 Example

```sql
SELECT name, salary 
FROM employees 
WHERE age > 30;
```

---

# 🟧 **Module 3 — Filtering, Sorting & Limiting**

### <img src="https://img.shields.io/badge/Progress-20%25-orange?style=flat-square"/>

### 📌 **Topics**

* 🧮 WHERE conditions
* ⚖ Operators: =, <>, >, <, BETWEEN, IN, LIKE
* ↕ ORDER BY
* 🔢 LIMIT

---

# 🟩 **Module 4 — SQL Joins (Core for DS Work)**

### <img src="https://img.shields.io/badge/Progress-35%25-green?style=flat-square"/>

### 📌 **Topics**

* 🔗 INNER JOIN
* 🔗 LEFT JOIN
* 🔗 RIGHT JOIN
* 🔗 FULL JOIN (concept)

### 📊 ASCII Diagram

```
employees                departments
-----------              -------------
id | name | dep_id  →    id | dep_name
```

---

# 🟪 **Module 5 — Aggregations & Grouping**

### <img src="https://img.shields.io/badge/Progress-50%25-purple?style=flat-square"/>

### 📌 **Topics**

* SUM(), AVG(), MAX(), MIN()
* COUNT()
* GROUP BY
* HAVING

### Example

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

---

# 🟥 **Module 6 — Subqueries**

### <img src="https://img.shields.io/badge/Progress-60%25-red?style=flat-square"/>

### 📌 **Topics**

* Subqueries in SELECT
* Subqueries in FROM
* Subqueries in WHERE

```
SELECT name
FROM employees
WHERE salary > (
     SELECT AVG(salary) FROM employees
);
```

---

# 🟫 **Module 7 — SQL Functions**

### <img src="https://img.shields.io/badge/Progress-70%25-brown?style=flat-square"/>

### 📌 **Topics**

### 🔤 **String Functions**

* CONCAT()
* LENGTH()
* LOWER(), UPPER()
* SUBSTRING()

### 📅 **Date Functions**

* NOW()
* DATE_ADD()
* YEAR(), MONTH()

### 🔢 **Numeric Functions**

* ROUND()
* CEIL(), FLOOR()

---

# 🟨 **Module 8 — Views, Indexes & Transactions (Basics Only)**

### <img src="https://img.shields.io/badge/Progress-80%25-yellow?style=flat-square"/>

### 📌 **Topics**

### 👁️ Views

* Creating views
* Updating through views

### ⚡ Indexes (DS-friendly intro)

* What is an index?
* How indexes speed up SELECT
* When NOT to use indexes

### 🔄 Transactions

* START TRANSACTION
* COMMIT / ROLLBACK

---

# 🟦 **Module 9 — Normalization & Data Modeling Basics**

### <img src="https://img.shields.io/badge/Progress-90%25-blue?style=flat-square"/>

### 📌 **Topics**

* Avoiding duplicate data
* Why DS needs clean, normalized tables

### Data Model Example

```
USER (id, name, email)
ORDER (id, user_id, total_amt)
PAYMENT (id, order_id, status)
```

---

# 🟧 **Module 10 — Analytical SQL (DS-Ready)**

### <img src="https://img.shields.io/badge/Progress-100%25-success?style=flat-square"/>

### 📌 **Topics**

* CASE WHEN
* Window Functions (Concept Only)
* Ranking & Partitioning use cases
* CTEs (WITH clauses) — essential for DS

### Example

```sql
WITH high_salaries AS (
    SELECT name, salary
    FROM employees
    WHERE salary > 100000
)
SELECT * FROM high_salaries;
```

---
