# SQL Query Documentation

## Purpose

This SQL query retrieves customer names from the `customers` table and applies string case transformations using SQL functions. It returns the first name in its original form, uppercase, and lowercase, along with the last name in uppercase.

## SQL Query

```sql
SELECT first_name, 
       UPPER(first_name), 
       UPPER(last_name), 
       LOWER(first_name)
FROM customers;
