# Average Pizza Per Order Query

This repository contains an SQL query to calculate the average number of pizzas per order from a dataset of pizza sales.

## Query Overview

The query calculates the **average number of pizzas per order** by summing up the total quantity of pizzas sold and dividing it by the number of unique orders. The result is formatted to two decimal places for better readability.

### SQL Query

```sql
SELECT CAST(
    CAST(SUM(quantity) AS DECIMAL(10, 2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10, 2))
    AS DECIMAL(10, 2)
) AS avg_pizza_per_order
FROM pizza_sales;
{
  "avg_pizza_per_order": "2.32"
}
