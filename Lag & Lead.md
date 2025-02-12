# SQL Query with LAG() and LEAD() Functions (with PARTITION BY and ORDER BY)
LAG() and LEAD() are window functions in SQL that provide a way to access data from a different row in the same result set without using a self-join. They are often used in data analysis to compare the current row with the previous or next row.

LAG() function fetches the value from a row that is a certain number of rows before the current row within the same result set. It's useful when you want to compare a value in a row with a value in a preceding row.

LEAD() function fetches the value from a row that is a certain number of rows after the current row within the same result set.

## Overview

The provided SQL query utilizes the `LAG()` and `LEAD()` window functions to access the previous and next rows' values for the `salary` column, respectively, within each `department` partition and ordered by `employee_id`. This query allows comparison of values within each department, considering the order of employees by their ID.

## SQL Query

```sql
SELECT *,
       LAG(salary) OVER (PARTITION BY department ORDER BY employee_id) AS lag_column,
       LEAD(salary) OVER (PARTITION BY department ORDER BY employee_id) AS lead_column
FROM employees;
