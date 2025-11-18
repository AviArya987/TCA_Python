# <img width="32" src="https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f40d.svg"> **Python Basics — Syllabus**

> A roadmap to learn Python fundamentals before entering Data Science, ML & AI.

<p align="center">
  <img width="600" src="https://svgshare.com/i/182x.svg">
</p>

---

## 🔥 **Progress Overview**

| Module                             | Status                                                                      |
| ---------------------------------- | --------------------------------------------------------------------------- |
| 📘 Mahine Execution                | ![badge](https://img.shields.io/badge/Progress-_%25-gray?style=flat-square) |
| 🧱 Python Foundations              | ![badge](https://img.shields.io/badge/Progress-_%25-gray?style=flat-square) |
| 📦 Data Structures                 | ![badge](https://img.shields.io/badge/Progress-_%25-gray?style=flat-square) |
| 🧮 Functions & Logic               | ![badge](https://img.shields.io/badge/Progress-_%25-gray?style=flat-square) |
| 🧪 Mini Projects                   | ![badge](https://img.shields.io/badge/Progress-_%25-gray?style=flat-square) |

---

## **1. 🧠 How Programs Run (Behind the Scenes)**

Understanding how a program actually runs inside a computer builds the foundation for all future skills. Here’s what happens under the hood:

---

### **🟦 1.1 — From Code to Execution**

When you write code (like Python), it’s just text.
To make it run, the computer goes through these steps:

Your Code (text)
      ↓
Python Interpreter reads it
      ↓
Converts to Bytecode (.pyc)
      ↓
Python Virtual Machine executes it

---

### **🟩 1.2 — What is an Interpreter?**

* Python is an **interpreted language**
* It reads your code **line-by-line**, executes it immediately
* This makes Python easier for beginners and great for data science

**Interpreter analogy:**
Think of Python as a translator standing between you and the computer:
You speak → Translator interprets → Computer executes.

---

### **🟧 1.3 — What is Bytecode?**

After reading your Python code, the interpreter converts it to something called **bytecode**:

* Not human-readable
* Not machine instructions
* A middle layer that makes Python fast

Example:
`print("Hello")` → converted to → internal bytecode instructions.

---

### **🟪 1.4 — Python Virtual Machine (PVM)**

The PVM is the “engine” of Python.

Its job:

* Take bytecode
* Execute it step-by-step
* Manage memory
* Handle errors

If bytecode is the “recipe”,
the PVM is the “chef” that cooks it.

---

### **🟥 1.5 — What About JIT Compilers?**

Some Python engines like **PyPy** use JIT (Just-In-Time) compilation:

* They convert frequently used code into machine code
* Makes Python much faster
* Useful in heavy data-science workloads

---

### **🟫 1.6 — Summary Flow Diagram**

👨‍💻 You write Python code
            ↓
📝 Interpreter reads code line-by-line
            ↓
⚙️ Converts to Bytecode
            ↓
🚀 Python Virtual Machine executes instructions
            ↓
🧮 CPU performs operations & Memory stores results

---
# 🧱 **2. Python Foundations**

### 📌 *Goal:* Build the base required for writing and understanding Python code.

### **🟣 Topics:**

* What is Python?
* Installing Python, Pip & VS Code
* Running Python files (`.py`)
* REPL, Jupyter Notebook, Anaconda
* Python Syntax
* Variables & Naming Rules
* Data Types (int, float, str, bool, None)
* Type Casting & Input/Output

### 🧩 **Inline SVG Visual — How Python Executes Code**

<svg width="600" height="130" xmlns="http://www.w3.org/2000/svg">
  <rect x="10" y="20" width="160" height="40" rx="10" fill="#1e1e1e" stroke="#6a5acd"/>
  <text x="30" y="47" fill="#fff" font-size="16" font-family="Arial">Python Code</text>

  <rect x="210" y="20" width="160" height="40" rx="10" fill="#1e1e1e" stroke="#50fa7b"/>
  <text x="245" y="47" fill="#fff" font-size="16" font-family="Arial">Interpreter</text>

  <rect x="410" y="20" width="160" height="40" rx="10" fill="#1e1e1e" stroke="#ffb86c"/>
  <text x="455" y="47" fill="#fff" font-size="16" font-family="Arial">Output</text>

  <line x1="170" y1="40" x2="210" y2="40" stroke="#fff" stroke-width="2"/>
  <line x1="370" y1="40" x2="410" y2="40" stroke="#fff" stroke-width="2"/>

  <polygon points="200,35 210,40 200,45" fill="#fff"/>
  <polygon points="400,35 410,40 400,45" fill="#fff"/>
</svg>


# 📦 **3. Core Data Structures**

### 🟣 Topics:

* Strings
* Lists
* Tuples
* Dictionaries
* Sets
* Indexing & Slicing
* Mutability vs Immutability
* Basic Operations
* Loops with Collections

### 🧩 **Visual — Data Types Overview**

<svg width="600" height="180">
  <text x="10" y="20" fill="#fff" font-size="18">Python Data Structures</text>

  <rect x="20" y="40" width="120" height="40" rx="8" fill="#1e1e1e" stroke="#ff79c6"/>
  <text x="50" y="65" fill="#fff">List</text>

  <rect x="160" y="40" width="120" height="40" rx="8" fill="#1e1e1e" stroke="#8be9fd"/>
  <text x="185" y="65" fill="#fff">Tuple</text>

  <rect x="300" y="40" width="120" height="40" rx="8" fill="#1e1e1e" stroke="#50fa7b"/>
  <text x="325" y="65" fill="#fff">Set</text>

  <rect x="440" y="40" width="120" height="40" rx="8" fill="#1e1e1e" stroke="#f1fa8c"/>
  <text x="455" y="65" fill="#000">Dict</text>
</svg>


---

# 🧮 **4. Functions & Logic Building**

### 🟣 Topics:

* `if / elif / else`
* Comparison & Logical Operators
* Loops: `for` and `while`
* `break`, `continue`, `pass`
* Defining Functions
* Parameters & Return Values
* Lambda Functions (light intro)

---

# 🔢 **5. Working With Files**

### 🟣 Topics:

* Reading files
* Writing files
* CSV basics
* Path handling
* `with open(...) as f:` structure

---

# 🧪 **6. Mini Projects (Beginner Level)**

### ✔ **Project 1: Student Score Analyzer**

* Read CSV
* Find highest/lowest score
* Plot chart

### ✔ **Project 2: Movie Dataset Explorer**

* Filter movies by rating
* Count genres

### ✔ **Project 3: Sales Data Summarizer**

* Load CSV
* Total sales
* Monthly grouping

---
