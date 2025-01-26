# SQL Query Explanation: UNION for Customer Classification

## Overview
This document explains the SQL query that categorizes customers into different groups based on their age, tipping behavior, and spending habits using the `UNION` operator.

## SQL Query
```sql
SELECT first_name, last_name, 'Old' 
FROM customers 
WHERE YEAR(birth_date) < 1960

UNION

SELECT first_name, last_name, 'Big Tipper' 
FROM customers c 
JOIN customer_orders co ON c.customer_id = co.customer_id 
WHERE tip > 3

UNION

SELECT first_name, last_name, 'Big Spender' 
FROM customers 
WHERE total_money_spent > 1000;
```

## Breakdown of the Query
1. **First Query (Old Customers):**
   - Selects customers born before 1960 and labels them as `'Old'`.

2. **Second Query (Big Tippers):**
   - Joins the `customers` table with the `customer_orders` table.
   - Selects customers who have given a tip greater than 3.
   - Labels them as `'Big Tipper'`.

3. **Third Query (Big Spenders):**
   - Selects customers who have spent more than $1000.
   - Labels them as `'Big Spender'`.

4. **UNION Operator:**
   - Combines results from all three queries into a single result set, ensuring unique records.

## Example Output
| first_name | last_name | Category     |
|------------|----------|-------------|
| John       | Doe      | Old         |
| Jane       | Smith    | Big Tipper  |
| Mike       | Johnson  | Big Spender |

## Use Case
This query is useful for segmenting customers into different categories for targeted marketing, personalized promotions, or customer behavior analysis.

## Notes
- `UNION` removes duplicate records. Use `UNION ALL` if duplicates should be retained.
- Ensure proper indexing on `customer_id` and `birth_date` for optimized performance.



