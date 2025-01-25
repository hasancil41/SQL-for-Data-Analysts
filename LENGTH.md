# Job Postings Data Analysis

## Overview
This project analyzes job postings data to extract meaningful insights. The SQL query below retrieves job titles along with their character lengths.

## SQL Query
```sql
SELECT job_title_short, LENGTH(job_title_short)
FROM job_postings_fact;
```

## Explanation
- `job_title_short`: Represents the abbreviated job title from the `job_postings_fact` table.
- `LENGTH(job_title_short)`: Calculates the number of characters in each job title.

## Usage
This query helps in understanding the distribution of job title lengths, which can be useful for text analysis, categorization, or data cleaning processes.

## Database Schema
The `job_postings_fact` table contains:
- `job_title_short` (VARCHAR) - The shortened job title.
- Additional columns related to job postings (not included in this query).



