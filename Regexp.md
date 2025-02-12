# SQL Query Using REGEXP for Pattern Matching

## Overview

This SQL query selects all columns from the `customers` table where the `first_name` matches a specified regular expression pattern. The regular expression used in this query is `'n'`, which will return all rows where the `first_name` contains the letter "n".

## SQL Query

```sql
SELECT *
FROM customers
WHERE first_name REGEXP 'n';
