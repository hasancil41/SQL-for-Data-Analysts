# SQL Query Using REGEXP_REPLACE Function

## Overview

This SQL query selects the `first_name` column from the `customers` table and uses the `REGEXP_REPLACE()` function to replace all occurrences of the letter `'a'` with `'k'` in the `first_name` column. This can be helpful for text manipulation tasks or batch replacements in string data.

## SQL Query

```sql
SELECT 
    first_name, REGEXP_REPLACE(first_name, 'a', 'k') AS modified_name
FROM
    customers;
