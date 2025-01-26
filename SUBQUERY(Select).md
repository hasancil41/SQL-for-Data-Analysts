# README

## SQL Query Explanation

This SQL query retrieves product details from the `ordered_items` table and calculates the percentage contribution of each product's quantity to the total quantity of all ordered items.

### Query Breakdown:

```sql
SELECT product_id, quantity, 
       (SELECT SUM(quantity) FROM ordered_items) AS sum_quantity, 
       (quantity / (SELECT SUM(quantity) FROM ordered_items) * 100) AS percent_of_quantity 
FROM ordered_items
ORDER BY percent_of_quantity DESC;
```

### Explanation of Each Clause:
1. **`SELECT product_id, quantity`**
   - Retrieves the `product_id` and `quantity` for each ordered item.

2. **`(SELECT SUM(quantity) FROM ordered_items) AS sum_quantity`**
   - Computes the total quantity of all ordered items.

3. **`(quantity / (SELECT SUM(quantity) FROM ordered_items) * 100) AS percent_of_quantity`**
   - Calculates the percentage of each product's quantity relative to the total quantity.

4. **`FROM ordered_items`**
   - Specifies that the data is coming from the `ordered_items` table.

5. **`ORDER BY percent_of_quantity DESC`**
   - Sorts the results in descending order based on the calculated percentage.

### Use Case:
- This query helps analyze which products contribute the most to overall order volume.
- Useful for inventory management and sales analysis.

### Potential Enhancements:
- Avoid redundant subqueries by using a `CROSS JOIN` to compute `SUM(quantity)` once.
- Use a Common Table Expression (CTE) for better readability and efficiency.

### Example Output:
| product_id | quantity | sum_quantity | percent_of_quantity |
|------------|---------|-------------|----------------------|
| 105        | 500     | 5000        | 10.00%               |
| 120        | 450     | 5000        | 9.00%                |
| 98         | 400     | 5000        | 8.00%                |


