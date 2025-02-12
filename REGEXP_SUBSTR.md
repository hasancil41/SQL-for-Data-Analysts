# SQL Query Using REGEXP_SUBSTR Function

## Overview

This SQL query selects the `first_name` column from the `customers` table and uses the `REGEXP_SUBSTR()` function to extract the first occurrence of the letter `'a'` from the `first_name` column. The function returns the matched substring, or `NULL` if no match is found.

## SQL Query

```sql
SELECT 
    first_name, REGEXP_SUBSTR(first_name, 'a') AS first_a_found
FROM
    customers;
