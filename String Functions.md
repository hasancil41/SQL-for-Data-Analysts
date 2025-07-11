# 🧵 SQL String Functions – Quick Guide

This project showcases essential SQL string functions with syntax and examples. It's a handy reference for learning and practicing string manipulation in SQL.

## 📌 Functions & Examples

### 🔢 LENGTH
Returns number of characters in a string:
```sql
SELECT LENGTH('SQL Rocks'); -- 9
```

### 🔠 UPPER / LOWER
Converts to uppercase or lowercase:
```sql
SELECT UPPER('sql');  -- 'SQL'
SELECT LOWER('SQL');  -- 'sql'
```

### ✂️ TRIM / LTRIM / RTRIM
Removes spaces:
```sql
SELECT TRIM('  SQL  ');    -- 'SQL'
SELECT LTRIM('  SQL');     -- 'SQL'
SELECT RTRIM('SQL  ');     -- 'SQL'
```

### ⬅️➡️ LEFT / RIGHT
Gets characters from left/right:
```sql
SELECT LEFT('Tutorial', 4);  -- 'Tuto'
SELECT RIGHT('Tutorial', 4); -- 'rial'
```

### 🔍 SUBSTRING
Extracts part of a string:
```sql
SELECT SUBSTRING('PostgreSQL', 5, 3); -- 'gre'
```

### 🔁 REPLACE
Replaces text in a string:
```sql
SELECT REPLACE('SQL is cool', 'cool', 'awesome'); -- 'SQL is awesome'
```

### 📍 LOCATE
Finds position of a substring:
```sql
SELECT LOCATE('is', 'SQL is powerful'); -- 5
```

### ➕ CONCAT
Joins strings:
```sql
SELECT CONCAT('SQL ', 'Functions'); -- 'SQL Functions'
```

## 🚀 How to Use

You can run these SQL queries in tools like MySQL Workbench, PostgreSQL, SQLite, or online editors like db-fiddle.com.



...
