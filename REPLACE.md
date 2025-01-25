# SQL Query Documentation

## Purpose

This SQL query replaces all occurrences of the letter 'A' with the letter 'Q' in the `job_title_short` column from the `job_postings_fact` table. This query is useful for text manipulation, such as data sanitization or transforming specific characters in job titles.

Explanation of Function

REPLACE(job\_title\_short, 'A', 'Q'): This function searches for all occurrences of the letter 'A' in the job\_title\_short column and replaces them with the letter 'Q'. It works case-sensitively, meaning it will only replace uppercase 'A' and not lowercase 'a'.SQL Query

```sql
SELECT REPLACE(job_title_short, 'A', 'Q') 
FROM job_postings_fact;
```
