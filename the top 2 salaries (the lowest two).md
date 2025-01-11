# SQL Query for Top 2 Salaries

## Objective

This query retrieves the top 2 salaries (the lowest two) from the `job_postings_fact` table, based on the `salary_year_avg` column. The salaries are ordered in ascending order.

## SQL Query

```sql
SELECT salary_year_avg 
FROM (
    SELECT salary_year_avg, ROW_NUMBER() OVER (ORDER BY salary_year_avg ASC) AS rn
    FROM job_postings_fact
) AS ranked_salaries
WHERE rn < 3;
