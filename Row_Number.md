# Job Postings Analysis

This repository contains an analysis of job postings with a focus on salaries and job titles. It includes a SQL query used to retrieve data about job positions, their average salaries, and their ranking within each job title.


##Explanation of the Query:

job_id: The unique identifier for each job posting.
job_title_short: The short title of the job.
salary_year_avg: The average salary for the job in a year.
row_number(): A window function that assigns a unique sequential integer to rows within each partition of job_title_short, ordered by salary_year_avg in descending order.

PARTITION BY: Divides the result set into partitions based on job_title_short, which ensures that each job title gets its own rank.
ORDER BY: Orders the rows within each partition by salary_year_avg in descending order, ensuring the highest salary comes first.

Purpose:
The query helps to identify the ranking of job titles based on their average salary. The results can be used to compare different job positions and their corresponding compensation.
## SQL Query

The query used in the analysis is as follows:

```sql
SELECT job_id,
       job_title_short,
       salary_year_avg,
       row_number() over(PARTITION BY job_title_short ORDER BY salary_year_avg DESC) as row_num
FROM job_postings_fact
WHERE salary_year_avg IS NOT NULL;


