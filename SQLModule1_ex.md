Here you go — **Module 1: MySQL Foundations**
**Assignments + Practice Problems + Output-Prediction Quiz (10 Qs)**
Designed for **beginners → aspiring Data Scientists**, with **icons + clean formatting**.

---

# 🧩 **MODULE 1 — MySQL Foundations**

### 📘 *Exercises, Assignments, Practice Problems & Output-Prediction Quiz*

---

# 🎯 **Section A — Output Prediction Quiz (10 Questions)**

Predict the output *without running the query*. Perfect for beginners.

---

## **📝 Q1**

**Table: `students`**

| id | name  | age |
| -- | ----- | --- |
| 1  | Asha  | 20  |
| 2  | Ravi  | 22  |
| 3  | Meera | 21  |

**Query:**

```sql
SELECT name, age FROM students WHERE age > 20;
```

**Your Output:** ?

---

## **📝 Q2**

**Query:**

```sql
SELECT 10 + 5 * 2;
```

---

## **📝 Q3**

```sql
SELECT LENGTH("MySQL");
```

---

## **📝 Q4**

```sql
SELECT LOWER("DaTaSciEnCe");
```

---

## **📝 Q5**

```sql
SELECT 15 / 4;
```

---

## **📝 Q6**

**Table: `sales`**

| id | amount |
| -- | ------ |
| 1  | 200    |
| 2  | 150    |
| 3  | 50     |

**Query:**

```sql
SELECT SUM(amount) FROM sales;
```

---

## **📝 Q7**

```sql
SELECT NOW();
```

*(What type of value does this return?)*

---

## **📝 Q8**

```sql
SELECT "A" = "a";
```

---

## **📝 Q9**

```sql
SELECT 100 MOD 30;
```

---

## **📝 Q10**

**Table: `users`**

| id | city   |
| -- | ------ |
| 1  | Mumbai |
| 2  | NULL   |
| 3  | Delhi  |

**Query:**

```sql
SELECT COUNT(city) FROM users;
```

---

---

# 📚 **Section B — Assignments (Module 1)**

---

## **📌 Assignment 1 — Create Your First Database**

✔ Create a new database named:

```
data_science_bootcamp
```

✔ Inside it, create a table:

```
students(id INT, name VARCHAR(50), marks INT)
```

✔ Insert 5 rows (any data).

✔ Write queries:

* Get all students
* Get students scoring above 70
* Get average marks
* Count number of students

---

## **📌 Assignment 2 — Explore Basic SQL Functions**

Create table:

```
products(id INT, title VARCHAR(50), price INT)
```

Add 5 items.

Run queries:

* MIN(price)
* MAX(price)
* AVG(price)
* LENGTH(title)
* UPPER(title)

Document your answers.

---

## **📌 Assignment 3 — WHERE Clause Mastery**

Create table:

```
employees(id INT, name VARCHAR(50), age INT, city VARCHAR(50))
```

Insert at least 5 rows.

Find:

1. Employees older than 30
2. Employees NOT from “Delhi”
3. Employees age between 25 and 35
4. Employees where city IS NULL
5. Employees whose name starts with ‘A’

---

## **📌 Assignment 4 — Build a Real Dataset**

Create a table:

```
orders(
  id INT,
  customer VARCHAR(50),
  amount DECIMAL(10,2),
  order_date DATE
)
```

Insert 10 rows.

Run:

* Total revenue
* Average order value
* Revenue for January
* Highest single order
* Count of orders per customer

---

---

# 🧠 **Section C — Practice Problems (Real DS Skills)**

(Perfect for strengthening fundamentals)

---

## **💡 Problem 1 — Find Top Scorer**

**Table: marks(id, student, score)**
Write query to get the **highest scoring student**.

---

## **💡 Problem 2 — Count Distinct Cities**

**Table: users(id, name, city)**
Find number of **unique cities**.

---

## **💡 Problem 3 — Calculate Discounted Price**

Add column `price_after_discount` = price – 10%

---

## **💡 Problem 4 — Filter Invalid Data**

Find records where:

* name is NULL
* or marks < 0

---

## **💡 Problem 5 — Simple Aggregation**

Given:
**Table: transactions(amount)**

Find:

* SUM
* MIN
* MAX
* COUNT

---

## **💡 Problem 6 — User Signup Statistics**

Table: users(joined_on DATE)

Find:

* Users who joined in 2024
* Users joined this month
* Users joined in the last 7 days

---

## **💡 Problem 7 — Average Age of Employees**

Find average age for employees older than 25.

---

## **💡 Problem 8 — Select First 3 Rows**

Use `LIMIT`.

---

## **💡 Problem 9 — Convert Names**

Convert all employee names to:

* UPPER
* LOWER
* LEFT 3 characters

---

## **💡 Problem 10 — Revenue Threshold**

Find orders with amount > average amount.

---

---

# 🎉 **DONE!**

If you want:
✅ Solutions key
✅ More advanced problems
✅ Visual diagrams (ERD, flowcharts)
✅ PDF or PPT version
Just say **“Generate next set”**
