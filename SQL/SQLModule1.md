# 📘 **Module 1 — MySQL Essentials**
---

# <img height="20" src="https://img.icons8.com/ios-filled/50/database.png"/> **1. Databases & MySQL Fundamentals**

### 🏷️ *Badge:* ![](https://img.shields.io/badge/Status-Foundation-blue)
---

### 📚 What is a Database?
A **database** is an organized collection of structured information, stored electronically and optimized for fast retrieval, updates, and processing.

### ✅ Why Databases Are Needed
- Store large amounts of data reliably  
- Retrieve information efficiently  
- Support multiple users at the same time  
- Prevent data loss  
- Provide security & consistency  
- Enable applications like banking, e-commerce, hospitals, social media  

### 🌍 Real-World Examples
- Instagram stores posts, likes, comments  
- Amazon stores products, orders, payments  
- Banks store accounts, balances, transactions  
- Colleges store students, courses, grades  

---

## 🏛️ 1.2 Types of Databases

### 🔷 Relational Databases (RDBMS)
- Store data in **tables**  
- Use **SQL**  
- Support **ACID** transactions  
- Ensure data integrity  

Examples: MySQL, PostgreSQL, Oracle, SQL Server

### 🟩 NoSQL Databases
- No fixed schema  
- Use documents, key-value pairs, graphs  
- Designed for scale and flexibility  

Examples: MongoDB, Cassandra, Redis

### 📌 Visual Comparison
```

Relational DB (Tables)        NoSQL (Documents)
+----+---------+              { "id": 1,
| id | name    |                "name": "John" }
+----+---------+

```

---

## 🐬 1.3 What is MySQL?

MySQL is a **Relational Database Management System (RDBMS)** known for its speed, reliability, and simplicity.

### ⭐ Why MySQL?
- Open-source  
- Easy for beginners  
- Used by major companies  
- Works beautifully with backend frameworks (Java/Spring Boot, Node.js, Python)  
- Great for scalable web applications  

### 🧩 Where MySQL is Used
- Facebook uses MySQL for core messaging  
- Uber uses it for geolocation + trip data  
- Airbnb uses MySQL for listings & bookings
---

## ⭐ 1.4 How SQL Works (Visual Explanation)

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

## 🖧 1.5 MySQL Client–Server Architecture

```

+----------------+        +------------------+
|  MySQL Client  | <----> |  MySQL Server    |
| (CLI/Workbench)|        | DB Engine        |
+----------------+        +------------------+

```

### 🟦 Client  
The interface where you **write SQL commands**.

### 🟥 Server  
The system that **stores & processes** the data.

---

## ⚙️ 1.6 Installing & Setting Up MySQL

### 📦 Install the following:
- MySQL Server  
- MySQL Workbench  

### 🎯 Verify Installation
```sql
SELECT VERSION();
```

---

## 🛠️ 1.7 MySQL Tools

### 🖥️  Command Line (mysql shell)

Fastest, preferred by developers.

### 🖼️ GUI Tools

* MySQL Workbench
* DBeaver
* TablePlus
* phpMyAdmin

---

## 📊 1.8 Understanding Schema, Tables, Rows, Columns

### 📁 Schema

A logical container for tables (like a folder).

### 📄 Table

Stores data in rows and columns.

### 🔢 Row

A single record.

### 🏷 Column

Defines the type of data stored.

### Example:

| id | name | age |
| -- | ---- | --- |
| 1  | John | 28  |
| 2  | Sara | 21  |

---

## 🧪 1.9 Your First SQL Commands

### ✔ Create a database

```sql
CREATE DATABASE school;
```

### ✔ Select the database

```sql
USE school;
```

### ✔ Create a table

```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  age INT
);
```

### ✔ Insert data

```sql
INSERT INTO students VALUES (1, 'John', 25);
INSERT INTO students VALUES (2, 'Sara', 22);
```

### ✔ Retrieve data

```sql
SELECT * FROM students;
```

---

# 📝 Exercises

### ✏️ Exercise 1

Create a database **company**.

### ✏️ Exercise 2

Create a table **employees** with:

* emp_id
* first_name
* last_name
* age
* salary

### ✏️ Exercise 3

Insert **5 employee records**.

### ✏️ Exercise 4

Write queries:

1. All employees
2. Employees older than 25
3. Employees earning more than 50,000

---

# 🧱 Mini-Assignment: Build a Library Database

Create schema **library_db** with:

### 📘 books

* book_id
* title
* author
* publication_year

### 🧑‍🤝‍🧑 members

* member_id
* name
* email

### 📄 borrow_records

* record_id
* member_id
* book_id
* borrow_date
* return_date

---

# 📝 End-of-Module Assignment

### ❗ Build a **College Management System**

Tables required:

* students
* courses
* enrollment
* departments

Queries to write:

* Students enrolled in a specific course
* All courses under a specific department
