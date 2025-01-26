# SQL Query Explanation: Self Join on Sequential Customer IDs

## Overview
This document explains the SQL query that performs a self-join on the `CUSTOMERS` table to find pairs of customers whose `customer_id` values are consecutive.

## SQL Query
```sql
SELECT c.customer_id, c.first_name, c.last_name, 
       ss.customer_id, ss.first_name, ss.last_name
FROM customers c
JOIN customers ss 
ON c.customer_id + 1 = ss.customer_id;
```

## Breakdown of the Query
1. **SELECT c.customer_id, c.first_name, c.last_name, ss.customer_id, ss.first_name, ss.last_name:**
   - Retrieves the `customer_id`, `first_name`, and `last_name` for both customers in the join.

2. **FROM customers c JOIN customers ss:**
   - The `customers` table is joined with itself (self-join), using aliases `c` and `ss` to represent two instances of the same table.

3. **ON c.customer_id + 1 = ss.customer_id:**
   - The join condition ensures that each customer is paired with the next sequential customer by matching `customer_id` values where `ss.customer_id` is exactly one greater than `c.customer_id`.

## Example Output
| c.customer_id | c.first_name | c.last_name | ss.customer_id | ss.first_name | ss.last_name |
|--------------|-------------|------------|--------------|-------------|------------|
| 100          | John        | Doe        | 101          | Jane        | Smith      |
| 101          | Jane        | Smith      | 102          | Mike        | Johnson    |

- Each row represents a pair of customers with consecutive `customer_id` values.

## Use Case
This query is useful when analyzing sequential relationships between customers, such as tracking customer sign-ups in consecutive order or identifying adjacent records in a dataset.

## Notes
- If `customer_id` values are not sequential (e.g., gaps exist), some customers may not have a matching pair.
- Ensure `customer_id` is indexed for better performance when running this query on large datasets.



