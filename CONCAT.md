# SQL Query Documentation

## Purpose

This SQL query extracts portions of the `phone` column from the `customers` table, retrieves specific segments (such as the area code, middle section, and last section), and then concatenates these segments to form a combined phone number without any delimiters.

Explanation of Functions

phone: The full phone number from the customers table.

SUBSTRING(phone, 1, 3): Extracts the first 3 characters from the phone number, which is typically the area code.

SUBSTRING(phone, 5, 3): Extracts the 3 characters starting from position 5, which represents the middle section of the phone number.

SUBSTRING(phone, 9, 4): Extracts the last 4 characters of the phone number.

CONCAT(SUBSTRING(phone, 1, 3), SUBSTRING(phone, 5, 3), SUBSTRING(phone, 9, 4)): Concatenates the extracted segments (area code, middle section, and last section) into a single string without any delimiters between them.

## SQL Query

```sql
SELECT phone, 
       SUBSTRING(phone, 1, 3) AS area_code,
       SUBSTRING(phone, 5, 3) AS mid_section,
       SUBSTRING(phone, 9, 4) AS last_section,
       CONCAT(SUBSTRING(phone, 1, 3), SUBSTRING(phone, 5, 3), SUBSTRING(phone, 9, 4)) AS formatted_phone
FROM customers;
```
