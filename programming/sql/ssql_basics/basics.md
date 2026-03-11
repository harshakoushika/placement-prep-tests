# SQL Basics

Structured Query Language (SQL) is used to interact with relational databases.

Common SQL operations include:

* Creating tables
* Inserting data
* Retrieving data
* Updating data
* Deleting data

---

## SELECT Statement

The SELECT statement retrieves data from a table.

Example:

```sql
SELECT * FROM employees;
```

This query returns all columns from the **employees** table.

---

## Selecting Specific Columns

```sql
SELECT name, salary
FROM employees;
```

---

## INSERT Statement

Used to add new records.

```sql
INSERT INTO employees (id, name, salary)
VALUES (1, 'Alice', 50000);
```

---

## UPDATE Statement

Used to modify existing records.

```sql
UPDATE employees
SET salary = 60000
WHERE id = 1;
```

---

## DELETE Statement

Used to remove records.

```sql
DELETE FROM employees
WHERE id = 1;
```
