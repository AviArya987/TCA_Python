# 🟥 Module 6 — SQL Joins  
### *Connect multiple tables and unlock meaningful relational insights.*

---

## 🎯 Learning Outcomes

After completing this module, we will be able to:

✔ Understand how relational tables connect  
✔ Use INNER, LEFT, RIGHT, FULL (workaround), CROSS, and SELF JOIN  
✔ Interpret join diagrams easily  
✔ Decide which join type fits a business scenario  
✔ Write real-world multi-table queries  

---

## 🔍 6.1 What Are Joins?

In relational databases, data is often stored **across multiple tables** instead of one large table.  
**Joins allow you to combine related data together.**

### 🧠 Real Example

| Table | Meaning |
|-------|---------|
| `employees` | Info about employees |
| `departments` | Department names |
| `orders` | Customer purchases |
| `customers` | Customer info |

Without joins, you would only see **half the story**.

---

## 🧩 6.2 Relational Tables Example

We will use the following two tables throughout this module:

### 🧑‍💼 employees

| id | name | dept_id |
|----|------|---------|
| 1 | John | 101 |
| 2 | Sarah | 102 |
| 3 | Adam | 101 |
| 4 | Lisa | 104 |

### 🏢 departments

| dept_id | dept_name |
|---------|-----------|
| 101 | IT |
| 102 | HR |
| 103 | Finance |
| 104 | Marketing |

---

### 🔗 ASCII Relationship Diagram

```

employees.dept_id  --->  departments.dept_id
(foreign key)         (primary key)

````

---

# 🔗 6.3 INNER JOIN

Returns matching rows **only where the relationship exists**.

### 🧠 Syntax

```sql
SELECT columns
FROM tableA
INNER JOIN tableB
ON tableA.key = tableB.key;
````

### ✔ Example

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.dept_id;
```

### 🧾 Result

| name  | dept_name |
| ----- | --------- |
| John  | IT        |
| Sarah | HR        |
| Adam  | IT        |
| Lisa  | Marketing |

🎯 **Use when:** You only want records with matching relationships.


📝 **Mini Task:**
Return only employees belong to **IT**.

---

# 🔗 6.4 LEFT JOIN

Returns **all rows from the left table**, even if there is **no match** on the right.

### ASCII Visual

```
LEFT JOIN = All Left + Matching Right
```

### ✔ Example

```sql
SELECT employees.name, departments.dept_name
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.dept_id;
```

### Output

| name  | dept_name |
| ----- | --------- |
| John  | IT        |
| Sarah | HR        |
| Adam  | IT        |
| Lisa  | Marketing |

*(Same result here because all match — but useful in real situations)*

---

📝 **Practice:**
List employees and show `"No Department"` if there's no match (use `COALESCE`).

---

# 🔗 6.5 RIGHT JOIN

Returns **all rows from the RIGHT table**, plus any matching rows from the left.

### ✔ Example

```sql
SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id;
```

### Result

| name  | dept_name |
| ----- | --------- |
| John  | IT        |
| Sarah | HR        |
| Adam  | IT        |
| Lisa  | Marketing |
| NULL  | Finance   |

---

🎯 **Use when:** You want everything from the referenced (right) table.

---

# 🔗 6.6 FULL JOIN (MySQL Workaround)

using `UNION`.

### ✔ Example

```sql
SELECT employees.name, departments.dept_name
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.dept_id

UNION

SELECT employees.name, departments.dept_name
FROM employees
RIGHT JOIN departments
ON employees.dept_id = departments.dept_id;
```

👍 **Use for:** Getting **all data**, whether matching or not.

---

# 🔗 6.7 CROSS JOIN

Creates every possible combination of rows from both tables.

```
employees × departments = all pairings
```

### ✔ Example

```sql
SELECT employees.name, departments.dept_name
FROM employees
CROSS JOIN departments;
```

⚠ Can produce **huge results** if tables are large.

---

# 🔗 6.8 SELF JOIN

A table joins to **itself** — used for hierarchy or parent-child relationships.

### Example — Employees reporting to managers

```sql
SELECT e.name AS employee, m.name AS manager
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.id;
```

---

# 🎯 6.9 Choosing the Right Join

| Join Type  | Returns                         | Use Case                         |
| ---------- | ------------------------------- | -------------------------------- |
| INNER JOIN | Matches only                    | When missing data isn't relevant |
| LEFT JOIN  | Everything left + matches right | Keep main table complete         |
| RIGHT JOIN | Everything right + matches left | Less common alternative          |
| FULL JOIN  | Everything                      | Need complete data overview      |
| CROSS JOIN | All combos                      | Testing or generating variations |
| SELF JOIN  | Joins same table                | Hierarchy or comparing rows      |

---


# 🧪 Quick Quiz

| Question                            | Correct Answer                   |
| ----------------------------------- | -------------------------------- |
| Join that keeps unmatched left rows | LEFT JOIN                        |
| Creates a Cartesian product         | CROSS JOIN                       |
| MySQL workaround for FULL JOIN      | `LEFT JOIN ... UNION RIGHT JOIN` |

---

# 🏋 Practice Exercises

Write queries to:

1️⃣ Show employees with their departments (INNER JOIN)
2️⃣ Show all departments even if no employees exist (RIGHT JOIN)
3️⃣ Show all employees even if missing departments (LEFT JOIN)
4️⃣ Create a full query combining both tables
5️⃣ Create a cart of **all pairs** of employees and departments (CROSS JOIN)

---

---

# 🎓 Final Assignment

Create:

* `customers`
* `orders`
* `products`

### Requirements:

✔ Join customers and orders
✔ Join orders and products
✔ Write:

* Orders with customer names
* Customers who haven't ordered (LEFT JOIN)
* Total spending per customer (`GROUP BY + JOIN`)

---

# 🏁 Module Summary

Understanding:

✔ What joins are and why they matter
✔ INNER, LEFT, RIGHT, FULL, CROSS & SELF JOIN
✔ How to visualize and choose the right join
✔ How to combine multiple tables into meaningful results

Just tell me.
```
