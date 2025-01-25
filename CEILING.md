# SQL Query Documentation

## Purpose

This SQL query retrieves the average hourly salary (`salary_hour_avg`) from the `job_postings_fact` table. It also calculates the ceiling value of `salary_hour_avg` using the `CEILING()` function. The query filters out rows where `salary_hour_avg` is `NULL`.

## SQL Query

```sql
SELECT salary_hour_avg, 
       CEILING(salary_hour_avg)
FROM job_postings_fact
WHERE salary_hour_avg IS NOT NULL;
