# Job Postings Fact Backup

This document provides details about the `job_postings_fact_backup` table, its purpose, structure, and how to use it effectively in maintaining and restoring data integrity for the `job_postings_fact` table.

---

## **Purpose**

The `job_postings_fact_backup` table serves as a backup for the original `job_postings_fact` table. It is intended to preserve the state of the data before running potentially destructive updates or modifications. This ensures that any unintentional changes can be reverted quickly and accurately.

---

## **Table Creation**

The backup table is created using the following SQL command:

```sql
CREATE TABLE job_postings_fact_backup AS
SELECT * FROM job_postings_fact;
