# SQL Query Documentation

## Purpose

This SQL query retrieves the `first_name` column from the `customers` table and uses the `LOCATE()` function to find the position of the substring 'Mic' within the `first_name`. This is useful for identifying customers with names that contain 'Mic' and determining where that substring first appears in each name.

Explanation of Function

first\_name: The first name of the customer from the customers table.

LOCATE('Mic', first\_name): The LOCATE() function searches for the first occurrence of the substring 'Mic' within the first\_name and returns the position where 'Mic' starts. If 'Mic' is not found, it returns 0.SQL Query

```sql
SELECT first_name, LOCATE('Mic', first_name)
FROM customers;
```
