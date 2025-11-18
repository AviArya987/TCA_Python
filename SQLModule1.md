# 📘 **Module 1 — MySQL Essentials for Data Science**
---

# <img height="20" src="https://img.icons8.com/ios-filled/50/database.png"/> **1. Databases & MySQL Fundamentals**

### 🏷️ *Badge:* ![](https://img.shields.io/badge/Status-Foundation-blue)

---

## ⭐ 1.1 What is a Database?

A **database** is an organized system that stores data in a structured manner so that it can be searched, queried, and analyzed efficiently.

### ✔ Why Data Science needs Databases?

* To fetch large datasets
* To clean & preprocess data
* To perform aggregations & analysis
* To join multiple data sources

### 📊 **Visual: Data Ecosystem**

```
+------------------------+
|   CSV / Excel Files    |
+------------------------+
             |
             v
+------------------------+
|    MySQL Database     |
|  (tables, relations)  |
+------------------------+
             |
             v
+--------------------------------------------+
|   Data Science Tools (Python, Pandas)     |
|   ML Models, Dashboards, Reports          |
+--------------------------------------------+
```

---

## ⭐ 1.2 How SQL Works (Visual Explanation)

### 🧠 “SQL is Declarative”

You describe **WHAT you want**, MySQL figures out **HOW to get it**.

### 🔍 **Query Flow Diagram (Inline SVG-style ASCII)**

```
  ┌──────────────────────────────────────────┐
  │              SQL Query                   │
  │   SELECT * FROM users WHERE age > 25;    │
  └──────────────────────────────────────────┘
                     |
                     v
        ┌─────────────────────────────┐
        │   MySQL Query Engine        │
        │  - Parser                   │
        │  - Optimizer                │
        │  - Executor                 │
        └─────────────────────────────┘
                     |
                     v
     ┌─────────────────────────────────┐
     │        Tables on Disk           │
     │   (rows, indexes, metadata)     │
     └─────────────────────────────────┘
                     |
                     v
        ┌─────────────────────────────┐
        │       Query Result          │
        └─────────────────────────────┘
```

---

## ⭐ 1.3 Understanding Tables, Rows, Columns

Tables are similar to Excel sheets but **more structured & relational**.

### 🎨 **Visual Table Example**

```
+----+----------+--------+------------+
| ID | Name     | Age    | City       |
+----+----------+--------+------------+
| 1  | Raj      | 28     | Mumbai     |
| 2  | Aditi    | 22     | Delhi      |
| 3  | John     | 34     | New York   |
+----+----------+--------+------------+
```

---

# <img height="20" src="https://img.icons8.com/ios-filled/50/source-code.png"/> **2. SQL Basics**

### 🏷️ *Badge:* ![](https://img.shields.io/badge/Level-Beginner-green)

---

## ⭐ 2.1 SQL Commands Cheat Sheet

| Category         | Commands                     | Icon |
| ---------------- | ---------------------------- | ---- |
| 📥 Data Query    | `SELECT`, `WHERE`            | 🔍   |
| ✏ Data Modify    | `INSERT`, `UPDATE`, `DELETE` | ✏    |
| 🏗 Schema Create | `CREATE`, `ALTER`, `DROP`    | 🧱   |
| 🔗 Relationship  | `JOIN`, `FOREIGN KEY`        | 🔗   |

---

## ⭐ 2.2 SELECT Queries (Core of SQL)

### 📘 Example:

```sql
SELECT name, age
FROM employees
WHERE age > 30;
```

### 🔍 Visual Flow:

```
Employees Table ➜ Filter age > 30 ➜ Show name + age
```

---

## ⭐ 2.3 Filtering Data (WHERE)

```sql
SELECT * FROM sales WHERE amount > 1000;
```

### 🎯 Real Use Case:

> "Find high-value transactions for analysis."

---

## ⭐ 2.4 Sorting & Limiting

```sql
SELECT *
FROM orders
ORDER BY order_date DESC
LIMIT 10;
```

---

# <img height="20" src="https://img.icons8.com/ios/50/connection.png"/> **3. Joins & Relationships**

### 🏷️ *Badge:* ![](https://img.shields.io/badge/Level-Essential-yellow)

---

## ⭐ 3.1 Types of Joins (Visual Diagram)

```
   Table A             Table B
+----------+      +-------------+
| user_id  |      | user_id     |
| name     |      | order_id    |
+----------+      +-------------+
       \            /
        \          /
         \        /
          \      /
           \    /
           JOIN
```

### JOIN Summary Table:

| Join          | Meaning                  | Visual |
| ------------- | ------------------------ | ------ |
| 🔹 INNER JOIN | Only matching data       | 🔗     |
| 🔹 LEFT JOIN  | All from left + matches  | ↩      |
| 🔹 RIGHT JOIN | All from right + matches | ↪      |
| 🔹 FULL JOIN  | All data                 | 🌐     |

---

## Example:

```sql
SELECT u.name, o.order_id
FROM users u
INNER JOIN orders o
ON u.id = o.user_id;
```

---

# <img height="20" src="https://img.icons8.com/ios/50/combo-chart.png"/> **4. Aggregations (Data Science Core)**

### 🏷️ *Badge:* ![](https://img.shields.io/badge/Level-Analytics-orange)

---

## ⭐ 4.1 Aggregation Functions

* `SUM()` — Total
* `AVG()` — Average
* `COUNT()` — Number of rows
* `MAX()` — Largest
* `MIN()` — Smallest

### Example:

```sql
SELECT city, AVG(salary)
FROM employees
GROUP BY city;
```

### 📊 Output Visual:

```
Mumbai → 82k
Delhi → 77k
NYC → 120k
```

---

# <img height="20" src="https://img.icons8.com/ios/50/layers.png"/> **5. Subqueries & Nested Logic**

### Example:

```sql
SELECT *
FROM employees
WHERE salary >
      (SELECT AVG(salary) FROM employees);
```

### Visual:

```
Calculate AVG Salary → Compare each row → Filter
```

---

# <img height="20" src="https://img.icons8.com/ios/50/view-file.png"/> **6. Views (Virtual Tables)**

### Example:

```sql
CREATE VIEW top_customers AS
SELECT name, total_spent
FROM customers
WHERE total_spent > 50000;
```

---

# <img height="20" src="https://img.icons8.com/ios/50/speed.png"/> **7. Indexing Basics**

Indexes make searches faster.

### ASCII Visual:

```
Without Index:   Full Scan 🔍🔍🔍🔍 
With Index:      Direct Jump 🎯
```

---

# <img height="20" src="https://img.icons8.com/ios/50/approve-and-update.png"/> **8. Transactions & ACID**

| Property | Meaning                    |
| -------- | -------------------------- |
| A        | Atomicity (all or nothing) |
| C        | Consistency                |
| I        | Isolation                  |
| D        | Durability                 |

---

# <img height="20" src="https://img.icons8.com/ios/50/organizational-structure.png"/> **9. Normalization & Data Modeling**

### Levels:

* 1NF — Atomic values
* 2NF — Remove partial dependencies
* 3NF — Remove transitive dependencies

---

# <img height="20" src="https://img.icons8.com/ios/50/combo-chart.png"/> **10. Analytical SQL for Data Science**

* Window Functions
* Ranking
* Running totals
* Percentiles
* Time-based analytics

### Example:

```sql
SELECT name, salary,
       RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```

---


