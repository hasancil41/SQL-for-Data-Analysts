# SQL Query - Job Title Salary Rank


Explanation:

job_title_short: The job title for the position.

salary_year_avg: The average salary for the job title.

rank(): A window function that assigns a rank to each row based on the ORDER BY clause. Here, it ranks the job titles in ascending order of their salary_year_avg.

ORDER BY salary_year_avg ASC: Orders the job titles by their average salary, from the lowest to the highest salary.

salary_rank: The rank assigned to each job title based on its average salary.

## Overview
This SQL query is designed to rank job titles based on their average annual salary (`salary_year_avg`). The `rank()` function is used with an `OVER` clause to assign a rank to each job title, ordered by the salary in ascending order.

## SQL Query

```sql
SELECT job_title_short,
       rank() OVER(ORDER BY salary_year_avg ASC) as salary_rank
FROM job_postings_fact;
