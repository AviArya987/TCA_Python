# 🟧 Module 3 — Filtering, Sorting & Limiting  
### *The skill of retrieving exactly the data you need.*

---

## 🎯 Learning Outcomes

After completing this module, we will be able to:

✔ Use the `WHERE` clause to filter rows  
✔ Apply comparison operators (`=`, `<>`, `>`, `<`, etc.)  
✔ Filter using `BETWEEN`, `IN`, and `LIKE`  
✔ Sort results using `ORDER BY`  
✔ Restrict returned rows using `LIMIT`  
✔ Recognize common mistakes and best practices  

---

## 📁 Sample Table Used in This Module

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
(5,'Paul Walker','Marketing',45000,'2021-11-20');
````

---

## 🧮 3.1 WHERE — Filtering Records

The `WHERE` clause filters rows based on a condition.

### 🧠 Syntax

```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### ✔ Example — IT Department Employees

```sql
SELECT name, department 
FROM employees
WHERE department = 'IT';
```

---

### 📝 Quick Practice

Retrieve employees who earn **more than 60,000**.

---


## ⚖ 3.2 Comparison Operators

| Operator     | Meaning          | Example              |
| ------------ | ---------------- | -------------------- |
| `=`          | equal to         | `salary = 70000`     |
| `<>` or `!=` | not equal        | `department <> 'HR'` |
| `>`          | greater than     | `salary > 60000`     |
| `<`          | less than        | `salary < 50000`     |
| `>=`         | greater or equal | `salary >= 55000`    |
| `<=`         | less or equal    | `salary <= 70000`    |

### ✔ Example — Employees hired before 2021

```sql
SELECT name, hire_date 
FROM employees
WHERE hire_date < '2021-01-01';
```

> ⚠ Always compare strings/dates inside quotes.

---

## 🎯 3.3 BETWEEN — Range Filter

Used for **number or date ranges (inclusive).**

### ✔ Example — Salaries between 50K and 80K

```sql
SELECT name, salary
FROM employees
WHERE salary BETWEEN 50000 AND 80000;
```

---

### 📝 Try This:

Find employees hired **between 2019 and 2021**.

---

## 📍 3.4 IN — Match Multiple Values

Use `IN` when you want to match from a set of values.

```sql
SELECT name, department 
FROM employees
WHERE department IN ('IT', 'Finance');
```

---

### 📝 Mini Exercise

Show employees from **HR, IT, or Marketing** departments.

---

## 🔍 3.5 LIKE — Pattern Searching

Use `LIKE` when searching text patterns.

| Pattern | Meaning                    |
| ------- | -------------------------- |
| `%`     | Any sequence of characters |
| `_`     | A single character         |

### ✔ Examples

```sql
-- Names starting with J
SELECT name FROM employees WHERE name LIKE 'J%';

-- Names ending with "n"
SELECT name FROM employees WHERE name LIKE '%n';

-- Contains "a"
SELECT name FROM employees WHERE name LIKE '%a%';
```

---

📌 **Real-life use case:** Searching users by partial text (name, phone, email).

---

## ↕ 3.6 ORDER BY — Sorting Output

Sort results in **ascending (ASC)** or **descending (DESC)** order.

### ✔ Highest salary first:

```sql
SELECT name, salary
FROM employees
ORDER BY salary DESC;
```

### ✔ Alphabetical order:

```sql
SELECT name
FROM employees
ORDER BY name ASC;
```

---

## 🔢 3.7 LIMIT — Control Result Count

Used to get a specific number of rows.

### ✔ Top 2 highest earners:

```sql
SELECT name, salary
FROM employees
ORDER BY salary DESC
LIMIT 2;
```

---

## 🌱 Bonus: NULL & Aliases

### ✔ Checking NULL values

```sql
SELECT * FROM employees WHERE salary IS NULL;
```

### ✔ Aliases for readability

```sql
SELECT name AS employee_name, salary AS yearly_pay
FROM employees;
```

---

# 🎓 Quick Quiz

| Question                        | Correct Query                                              |
| ------------------------------- | ---------------------------------------------------------- |
| Get employees who earn over 60k | `SELECT * FROM employees WHERE salary > 60000;`            |
| Find names starting with S      | `SELECT * FROM employees WHERE name LIKE 'S%';`            |
| Get top 3 newest hires          | `SELECT * FROM employees ORDER BY hire_date DESC LIMIT 3;` |

---

# 🧪 Exercises

### 🏋 Task Set

1️⃣ Fetch all employees from IT
2️⃣ Show employees earning less than 55,000
3️⃣ List employees whose name contains `o`
4️⃣ Sort salary ascending
5️⃣ Show only 3 results


---

# 📚 Final Assignment (Graded)

Create a table `products` with:

| Column     | Type         |
| ---------- | ------------ |
| product_id | INT          |
| name       | VARCHAR(100) |
| category   | VARCHAR(50)  |
| price      | INT          |
| added_date | DATE         |

### Small Tasks:

✔ Insert **at least 6 sample products**
✔ Find products priced **between 100 and 500**
✔ Sort by price (highest first)
✔ Show products where name contains the letter `a`
✔ Show the **top 2 cheapest products**

---

# 🏁 Module Summary

Understanding:

✔ Filtering using `WHERE`
✔ Using operators for precise queries
✔ Pattern search with `LIKE`
✔ Sorting using `ORDER BY`
✔ Returning limited results with `LIMIT`

---

