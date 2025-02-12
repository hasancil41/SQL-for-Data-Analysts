# SQL Query with LAG() and LEAD() Functions (with PARTITION BY and ORDER BY)

## Overview

The provided SQL query utilizes the `LAG()` and `LEAD()` window functions to access the previous and next rows' values for the `salary` column, respectively, within each `department` partition and ordered by `employee_id`. This query allows comparison of values within each department, considering the order of employees by their ID.

## SQL Query

```sql
SELECT *,
       LAG(salary) OVER (PARTITION BY department ORDER BY employee_id) AS lag_column,
       LEAD(salary) OVER (PARTITION BY department ORDER BY employee_id) AS lead_column
FROM employees;
