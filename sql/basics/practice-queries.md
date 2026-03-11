# SQL Practice Queries

Assume the following table:

employees

| id | name    | department | salary |
| -- | ------- | ---------- | ------ |
| 1  | Alice   | HR         | 50000  |
| 2  | Bob     | IT         | 60000  |
| 3  | Charlie | IT         | 55000  |
| 4  | David   | Finance    | 70000  |

---

## Problem 1: Retrieve All Employees

```sql
SELECT * FROM employees;
```

---

## Problem 2: Select Only Names

```sql
SELECT name FROM employees;
```

---

## Problem 3: Employees from IT Department

```sql
SELECT *
FROM employees
WHERE department = 'IT';
```

---

## Problem 4: Employees with Salary > 55000

```sql
SELECT name, salary
FROM employees
WHERE salary > 55000;
```

---

## Problem 5: Sort Employees by Salary

```sql
SELECT *
FROM employees
ORDER BY salary DESC;
```
