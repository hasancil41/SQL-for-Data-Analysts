# SQL Query Using REGEXP_INSTR Function

## Overview

This SQL query selects the `first_name` column from the `customers` table and uses the `REGEXP_INSTR()` function to find the position of the first occurrence of the letter `'a'` within each `first_name`. The function returns the position of the match, or `0` if no match is found.

## SQL Query

```sql
SELECT 
    first_name, REGEXP_INSTR(first_name, 'a') AS position_of_a
FROM
    customers;
