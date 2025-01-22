# Query to Retrieve City Names Based on Vowel Conditions

This SQL query retrieves the list of unique city names from the `STATION` table that meet the following conditions:

- The city name does **not start with a vowel** (`A, E, I, O, U`), or
- The city name does **not end with a vowel** (`a, e, i, o, u`).

```sql
-- Retrieve unique city names from the STATION table
-- where city names do not start or end with vowels.

SELECT DISTINCT CITY
FROM STATION
WHERE (CITY NOT LIKE 'A%'     -- Does not start with 'A'
       AND CITY NOT LIKE 'E%' -- Does not start with 'E'
       AND CITY NOT LIKE 'I%' -- Does not start with 'I'
       AND CITY NOT LIKE 'O%' -- Does not start with 'O'
       AND CITY NOT LIKE 'U%') -- Does not start with 'U'
   OR (CITY NOT LIKE '%a'     -- Does not end with 'a'
       AND CITY NOT LIKE '%e' -- Does not end with 'e'
       AND CITY NOT LIKE '%i' -- Does not end with 'i'
       AND CITY NOT LIKE '%o' -- Does not end with 'o'
       AND CITY NOT LIKE '%u'); -- Does not end with 'u'
```

## Explanation

### Key Components of the Query

1. **`DISTINCT`**:
   - Ensures that duplicate city names are removed from the result set.

2. **Conditions**:
   - **First condition**: Filters out city names that start with the vowels `A`, `E`, `I`, `O`, or `U`.
   - **Second condition**: Filters out city names that end with the vowels `a`, `e`, `i`, `o`, or `u`.

3. **`OR` Logic**:
   - A city is included if **either**:
     - It does not start with a vowel, **OR**
     - It does not end with a vowel.

4. **Comments in Query**:
   - Inline comments clarify each condition for readability.

### Usage

- **Database Compatibility**:
  - Works with most SQL databases, including MySQL, PostgreSQL, Oracle, and SQL Server.

- **Output**:
  - A list of unique city names that satisfy the specified conditions.

Copy and paste the query into your SQL environment to test its functionality!
