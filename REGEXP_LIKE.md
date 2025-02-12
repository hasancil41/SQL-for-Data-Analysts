# SQL Query Using REGEXP_LIKE Function

## Overview

This SQL query selects the `first_name` column from the `customers` table and uses the `REGEXP_LIKE()` function to check if the `first_name` matches a specified regular expression pattern. In this case, the pattern is `'a'`, which checks if the `first_name` contains the letter `'a'`.

## SQL Query

```sql
SELECT 
    first_name, REGEXP_LIKE(first_name, 'a') AS contains_a
FROM
    customers;
