# SQL Query Explanation: GROUP BY with ROLLUP

## Overview
This document explains the SQL query that uses `GROUP BY` with `ROLLUP` to aggregate customer spending data.

## SQL Query
```sql
SELECT customer_id, SUM(total_money_spent)
FROM CUSTOMERS
GROUP BY customer_id WITH ROLLUP;
```

## Breakdown of the Query
1. **SELECT customer_id, SUM(total_money_spent):**
   - Retrieves the `customer_id` and calculates the total money spent by each customer using the `SUM()` function.

2. **FROM CUSTOMERS:**
   - Specifies the source table containing customer transaction data.

3. **GROUP BY customer_id WITH ROLLUP:**
   - Groups the data by `customer_id` and calculates the total spending per customer.
   - The `WITH ROLLUP` modifier adds an extra row containing the grand total (sum of all customers' total spending).

## Example Output
| customer_id | SUM(total_money_spent) |
|------------|------------------------|
| 101        | 500                     |
| 102        | 750                     |
| 103        | 300                     |
| NULL       | 1550                    |

- The last row (`NULL`) represents the grand total of all customers' total spending.

## Use Case
Using `ROLLUP` is helpful when generating reports where both individual totals and an overall total are required, reducing the need for additional queries.

## Notes
- If you need distinct customer totals without a grand total, omit `WITH ROLLUP`.
- Some databases might require enabling `ROLLUP` or using alternative syntax.



