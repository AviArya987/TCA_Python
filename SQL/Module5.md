# 🟫 Module 5 — Constraints & Data Integrity  
### *Making sure data stays valid, and meaningful.*

---

## 🎯 Learning Objectives

By the end of this module, we will be able to:

✔ Understand why constraints matter  
✔ Create tables with constraints  
✔ Apply PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK & DEFAULT  
✔ Enforce referential integrity with cascading rules  
✔ Avoid common mistakes when designing relational tables  

---

## 🧩 5.1 What Are Constraints?

🔍 **Constraints** are rules applied to database columns or tables that enforce **data accuracy, consistency, and validity**.

📌 Example benefits:

- Prevent duplicate records  
- Ensure required fields are not empty  
- Maintain logical relationships between tables  
- Enforce business rules  

---

### 💡 Real-World Examples

| Business Rule | Database Constraint |
|--------------|---------------------|
| Every student must have a unique ID | PRIMARY KEY |
| Email cannot be duplicated | UNIQUE |
| Age cannot be negative | CHECK |
| Department assigned must exist in departments table | FOREIGN KEY |

---

# 🧱 5.2 NOT NULL — No Empty Values Allowed

Ensures a column **must contain a value**.

### 🧠 Syntax

```sql
column_name datatype NOT NULL
````

### ✔ Example

```sql
CREATE TABLE students (
  id INT,
  name VARCHAR(50) NOT NULL
);
```

⚠ Without NOT NULL, missing names would be allowed.


📝 **Exercise:**
Add a new column `email` that **must not be empty**.

---

# 🏷 5.3 DEFAULT — Auto Assign Value if None Provided

Assigns a **fallback value** when no value is inserted.

### 🧠 Example

```sql
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  role VARCHAR(50) DEFAULT 'Staff'
);
```

```sql
INSERT INTO employees (id, name) VALUES (1, 'John');
```

👀 Result: `role = 'Staff'` automatically.

📝 **Try:**
Add a column `status` with default `'Active'`.

---

# 🔑 5.4 PRIMARY KEY — Unique Identifier for Each Row

A Primary Key ensures:

* Value must be **unique**
* Value **cannot be NULL**

### 🧠 Syntax

```sql
id INT PRIMARY KEY
```

### ✔ Example

```sql
CREATE TABLE departments (
  dept_id INT PRIMARY KEY,
  dept_name VARCHAR(50)
);
```

⭐ **Best Practice:** Every table should have **one primary key**.

---

# 🔒 5.5 UNIQUE — No Duplicate Allowed

Ensures values in a column are **never repeated**.

### Example — Enforce unique email:

```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  email VARCHAR(100) UNIQUE
);
```

⚠ Common mistake:
`UNIQUE` ≠ `PRIMARY KEY`
A table can have **many UNIQUE columns**, but only **one PRIMARY KEY**.

📝 **Try:**
Ensure `phone_number` in a `customers` table is unique.

---

# ✔ 5.6 CHECK — Enforce User Rules

Used to validate data with custom conditions.

### Example

```sql
CREATE TABLE products (
  id INT PRIMARY KEY,
  price INT CHECK (price > 0)
);
```

⛔ You cannot insert:

```sql
INSERT INTO products VALUES (1, -50);
```

📝 **Challenge:**
Ensure `age >= 18` in a `citizens` table.

---

# 🔗 5.7 FOREIGN KEY — Relationship Between Tables

A **Foreign Key** ensures a value exists in another table before inserting.

### 🧠 Example

```sql
CREATE TABLE departments (
  dept_id INT PRIMARY KEY,
  dept_name VARCHAR(50)
);

CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  dept_id INT,
  FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);
```

💡 This prevents assigning employees to *non-existent* departments.

---

# 🧬 5.8 Referential Integrity

Ensures that **related data stays logically consistent**.

📌 Examples of violations:

* A student references a deleted class
* An order references a missing customer

Foreign Keys prevent such invalid links.

---

# 🔁 5.9 Cascading Rules — Maintain Relationships Automatically

Used with `FOREIGN KEY` to control what happens when a referenced row is updated/deleted.

| Rule                | Meaning                                 |
| ------------------- | --------------------------------------- |
| `ON DELETE CASCADE` | Delete child rows automatically         |
| `ON UPDATE CASCADE` | Updates propagate                       |
| `SET NULL`          | Replace broken links with NULL          |
| `RESTRICT`          | Prevent action if related records exist |

### Example

```sql
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  dept_id INT,
  FOREIGN KEY (dept_id)
  REFERENCES departments(dept_id)
  ON DELETE CASCADE
  ON UPDATE CASCADE
);
```

⚠ **Warning:**
Cascades can delete **large connected data chains accidentally.**
Use responsibly.

---

# 🧪 Mini Quiz

| Question                    | Correct Answer |
| --------------------------- | -------------- |
| Prevents empty values       | `NOT NULL`     |
| Ensures unique values       | `UNIQUE`       |
| Relationship between tables | `FOREIGN KEY`  |
| Creates automatic value     | `DEFAULT`      |
| Validates business logic    | `CHECK`        |

---

# 🏋 Practice Exercises

Write SQL to:

1️⃣ Create `courses` table with:

* `course_id` (primary key)
* `title` (NOT NULL)

2️⃣ Create `students` table with:

* `student_id` primary key
* `name` NOT NULL
* `course_id` referencing `courses.course_id`

3️⃣ Add CHECK constraint that marks cannot exceed **100**.

---

# 🎓 Final Assignment — Library System (Graded)

Create the following:

📘 `books` table

* `book_id` (PK)
* `title` (NOT NULL)
* `category`
* `price` CHECK (price > 0)

🧑‍🤝‍🧑 `members` table

* `member_id` (PK)
* `name`
* `email` (UNIQUE)

📄 `borrowed_books` table

* `record_id` (PK)
* `book_id` (FK)
* `member_id` (FK)
* `borrow_date` DEFAULT CURRENT_DATE
* Apply `ON DELETE CASCADE`

---

# 🏁 Module Summary

Understanding:

✔ Why constraints matter
✔ How to prevent invalid, duplicated, or missing records
✔ How relationships and cascading rules protect data
✔ How constraints enforce real-world business rules
