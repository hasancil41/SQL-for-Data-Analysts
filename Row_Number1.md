# SQL Query - Top 2 Orders per Customer

## Purpose
This SQL query selects the top 2 highest order totals and corresponding tips for each customer from the `customer_orders` table. It combines information from the `customer_orders` and `customers` tables, displaying customer details and their respective top 2 orders.

## Full SQL Query

```sql
SELECT *
FROM (
    SELECT 
        co.customer_id,
        c.first_name,
        c.last_name,
        co.order_total,
        co.tip,
        ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_total DESC) AS row_num
    FROM customer_orders AS co
    JOIN customers AS c ON co.customer_id = c.customer_id
) AS row_table
WHERE row_num < 3;
