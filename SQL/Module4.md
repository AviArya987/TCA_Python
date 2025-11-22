# 🟩 Module 4 — Advanced SELECT & Query Operations  
### *Level up SQL querying power with grouping, aggregation, subqueries, and smarter filtering.*

---

## 🔁 Quick Recap from Previous Module

Before diving in, remember:

- `WHERE` filters rows  
- `ORDER BY` sorts results  
- `LIMIT` restricts returned data  
- `LIKE`, `BETWEEN`, and `IN` help refine searches  

Now, we build on these skills with **advanced query operations**.

---

## 📁 Sample Table Used Throughout

```sql
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  department VARCHAR(50),
  salary INT,
  hire_date DATE
);

INSERT INTO employees VALUES
(1,'John Doe','IT',70000,'2020-01-15'),
(2,'Sarah King','HR',55000,'2019-06-10'),
(3,'Adam Smith','Finance',90000,'2018-03-25'),
(4,'Lisa Brown','IT',60000,'2022-08-01'),
(5,'Paul Walker','Marketing',45000,'2021-11-20'),
(6,'Emily Clark','Finance',90000,'2020-04-13');
````

---

# 🧩 4.1 DISTINCT — Remove Duplicates

`DISTINCT` ensures unique values are returned.

### 🧠 Syntax

```sql
SELECT DISTINCT column_name
FROM table_name;
```

### Example — Unique Departments

```sql
SELECT DISTINCT department 
FROM employees;
```

### Expected Output

| department |
| ---------- |
| IT         |
| HR         |
| Finance    |
| Marketing  |


📝 **Try It:**
Show distinct salary values from the table.

---

# 🎯 4.2 Advanced Filters — BETWEEN, IN, LIKE (Short Review + New Use)

### ✔ RANGE Filter — BETWEEN

```sql
SELECT name, salary
FROM employees
WHERE salary BETWEEN 60000 AND 90000;
```

### ✔ Multiple Values — IN

```sql
SELECT name, department
FROM employees
WHERE department IN ('IT', 'Finance');
```

### ✔ Pattern Search — LIKE

```sql
SELECT name FROM employees 
WHERE name LIKE '%a%';
```

📝 **Try It:**
Return employees hired between **2020 and 2022**.

---

# 📊 4.3 Aggregate Functions

Aggregate functions perform calculations on groups of rows.

| Function | Meaning        |
| -------- | -------------- |
| COUNT()  | Counts records |
| SUM()    | Total          |
| AVG()    | Average        |
| MIN()    | Smallest value |
| MAX()    | Largest value  |

### Example — Count Total Employees

```sql
SELECT COUNT(*) AS total_employees
FROM employees;
```

### Example — Average Salary

```sql
SELECT AVG(salary) AS avg_salary
FROM employees;
```

📝 **Try It:**
Find the **highest** salary.

---

# 🧱 4.4 GROUP BY — Grouping Rows

Used with aggregates to summarize data by category.

### 🧠 Syntax

```sql
SELECT column, aggregate_function(column)
FROM table
GROUP BY column;
```

### Example — Salary per Department

```sql
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department;
```

### Expected Output

| department | avg_salary |
| ---------- | ---------- |
| IT         | 65000      |
| HR         | 55000      |
| Finance    | 90000      |
| Marketing  | 45000      |

---

# 🧮 4.5 HAVING — Filter AFTER Aggregation

`WHERE` cannot filter aggregated results — that's what `HAVING` is for.

### ❌ Incorrect

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department
WHERE AVG(salary) > 60000;
```

### ✔ Correct

```sql
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING avg_salary > 60000;
```

📝 **Try It:**
Show only departments with **more than 1 employee**.

---

# 🏷 4.6 Aliases — Shortening Names

Aliases rename columns or tables for readability.

### ✔ Column Alias

```sql
SELECT name AS employee_name
FROM employees;
```

### ✔ Table Alias

```sql
SELECT e.name, e.salary
FROM employees AS e;
```

💡 **Tip:** Aliases help with large queries and joins (Module 5).

---

# ⚡ 4.7 CASE Expression — Conditional Logic in SQL

`CASE` allows custom computed fields.

### Example — Salary Category

```sql
SELECT 
  name,
  salary,
  CASE 
    WHEN salary >= 80000 THEN 'High'
    WHEN salary BETWEEN 50000 AND 79999 THEN 'Medium'
    ELSE 'Low'
  END AS salary_group
FROM employees;
```

📝 **Try It:**
Mark employees hired before 2020 as `"Senior"` and others as `"Junior"`.

---

# 🧠 4.8 Subqueries — Query Inside a Query

### ✔ Basic Subquery

```sql
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### ✔ Nested Subquery Example

```sql
SELECT name
FROM employees
WHERE department IN (
  SELECT department 
  FROM employees 
  GROUP BY department
  HAVING COUNT(*) > 1
);
```

📝 **Try It:**
Get employees earning more than the **minimum salary**.

---

# 🧪 Mini Quiz

| Question                       | Correct Example                    |
| ------------------------------ | ---------------------------------- |
| Remove duplicate values        | `SELECT DISTINCT(col) FROM table;` |
| Filter aggregated results      | `HAVING`                           |
| Calculate total salary         | `SUM(salary)`                      |
| Create conditional result text | `CASE WHEN … THEN … END`           |

---

# 🏋 Practice Exercises

Write SQL queries for:

1️⃣ All unique departments
2️⃣ Count employees per department
3️⃣ Highest salary in the company
4️⃣ Departments with average salary > 60,000
5️⃣ Employees whose salary > average salary
6️⃣ List employees with a label: `"Top Performer"` (salary ≥ 80k)

---

# 🎓 Final Assignment (Graded)

Create a table:

```sql
CREATE TABLE sales (
  id INT PRIMARY KEY,
  product VARCHAR(50),
  category VARCHAR(50),
  price INT,
  sale_date DATE
);
```

### Task Requirements

✔ Insert at least 8 sample rows
✔ Show distinct categories
✔ Count sales per category
✔ Show categories with total revenue > 50,000
✔ Label products as `"Expensive"`, `"Moderate"`, or `"Budget"`
✔ Return products priced above the **average price** using a subquery

---

# 🏁 Module Summary

You we understand:

✔ DISTINCT
✔ Advanced filtering patterns
✔ Aggregations with `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
✔ GROUP BY and HAVING
✔ CASE expressions for custom logic
✔ Subqueries (basic + nested)

