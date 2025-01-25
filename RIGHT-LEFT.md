# SQL Query Documentation

## Purpose

This SQL query retrieves the first 4 characters from the `job_title_short` column and the last 3 characters from the same column in the `job_postings_fact` table. It is used for extracting specific portions of the job title to help with text analysis or processing.

Explanation of Functions

LEFT(job\_title\_short, 4): Extracts the first 4 characters from the job\_title\_short column.

RIGHT(job\_title\_short, 3): Extracts the last 3 characters from the job\_title\_short column.SQL Query

```sql
SELECT LEFT(job_title_short, 4), 
       RIGHT(job_title_short, 3)
FROM job_postings_fact;
```
