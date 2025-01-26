# Project Title: Customer Order Analysis

## Overview:

This project involves analyzing customer orders from a retail or restaurant platform. It includes extracting and formatting order dates to better understand purchasing patterns.

## Objective:

The goal is to query the `customer_orders` table, extract the order dates, and format them for improved readability.

## **Explanation:**

order\_date: This is the raw order date field from the customer\_orders table.

DATE\_FORMAT(order\_date, '%M %D %Y'): This formats the order\_date to display the full month name, the day of the month with a suffix (e.g., 25th), and the full year (e.g., 2025).

SQL Query:

The following query retrieves the order dates and formats them:

```sql
SELECT order_date, DATE_FORMAT(order_date, '%M %D %Y')
FROM customer_orders;
```
