# SQL Query Documentation

## Purpose

This SQL query extracts portions of the `phone` column from the `customers` table. Specifically, it retrieves the area code, the next set of three digits, and the final four digits, effectively breaking down the phone number into its components.

Explanation of Functions

phone: The full phone number from the customers table.

SUBSTRING(phone, 1, 3): Extracts the first 3 characters from the phone number, representing the area code.

SUBSTRING(phone, 5, 3): Extracts the 3 characters starting from position 5, representing the middle section of the phone number.

SUBSTRING(phone, 9, 4): Extracts the last 4 characters from the phone number.SQL Query

```sql
SELECT phone, 
       SUBSTRING(phone, 1, 3) AS area_code,
       SUBSTRING(phone, 5, 3) AS mid_section,
       SUBSTRING(phone, 9, 4) AS last_section
FROM customers;
```
