# SQL Project Tutorial

Step-by-step SQL project walkthrough for employee analytics.

## Project: Employee Database Analysis

### Step 1: Create Database

```sql
CREATE DATABASE company_db;
USE company_db;
```

### Step 2: Create Tables and Sample Data

```sql
CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50)
);

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id)
);

INSERT INTO departments VALUES
(1, 'Engineering'),
(2, 'Sales'),
(3, 'Marketing');

INSERT INTO employees VALUES
(1, 'Ada', 'Lovelace', 95000, 1),
(2, 'Grace', 'Hopper', 105000, 1),
(3, 'Alan', 'Turing', 88000, 1),
(4, 'Katherine', 'Johnson', 92000, 2),
(5, 'Nikola', 'Tesla', 87000, 3);
```

### Step 3: Analyze Data

```sql
-- Average salary by department
SELECT d.department_name, ROUND(AVG(e.salary), 2) AS avg_salary
FROM employees e
JOIN departments d ON e.department_id = d.department_id
GROUP BY d.department_name
ORDER BY avg_salary DESC;

-- Top earners
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary DESC
LIMIT 3;
```

### Step 4: Window Function (Optional)

```sql
SELECT
    first_name,
    last_name,
    department_id,
    salary,
    RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) AS dept_rank
FROM employees;
```

---

## Try next

- Add indexes on `department_id` and compare query plans
- Write the same aggregations in Python with SQLAlchemy or pandas `read_sql`
- Continue to [sql-database.md](sql-database.md) for ORMs and production patterns
