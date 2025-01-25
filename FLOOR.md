# SQL Query Documentation

## Purpose

This SQL query is designed to retrieve the average hourly salary (`salary_hour_avg`) from the `job_postings_fact` table. It also computes the floor of the `salary_hour_avg` using the `FLOOR()` function. The query filters out rows where the `salary_hour_avg` value is `NULL`.

## SQL Query

```sql
SELECT salary_hour_avg, FLOOR(salary_hour_avg)
FROM job_postings_fact
WHERE salary_hour_avg IS NOT NULL;
