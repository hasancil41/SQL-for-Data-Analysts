# SQL Query Documentation

## Purpose

This SQL query retrieves job titles from the `job_postings_fact` table and applies various trimming functions to remove unwanted whitespace from the `job_title_short` column. The query helps in cleaning and standardizing job title data.

Explanation of Functions

TRIM(job\_title\_short): Removes any leading and trailing whitespace from job\_title\_short.

LTRIM(job\_title\_short): Removes only leading (left-side) whitespace from job\_title\_short.

RTRIM(job\_title\_short): Removes only trailing (right-side) whitespace from job\_title\_short.SQL Query

```sql
SELECT TRIM(job_title_short), 
       LTRIM(job_title_short), 
       RTRIM(job_title_short)
FROM job_postings_fact;
```





