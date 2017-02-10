# Grouping Functions (MIN, MAX, COUNT, etc.)

## Example #1 (MAX)
Returns maximum salary (sal).
```sql
SELECT MAX(sal) AS MAXIMUM
FROM emp;
```

## Example #2 (MIN)
Returns minimum salary (sal).
```sql
SELECT MIN(sal) AS MINIMUM
FROM emp;
```

## Example #3 (SUM)
Returns the sum of all salary (sal).
```sql
SELECT SUM(sal) AS "Total Salary"
FROM emp;
```

## Example #4 (COUNT)
Returns the count(number of occurrences) of rows or data points. (i.e. 14 rows in table, therefore the COUNT function returns 14)
```sql
SELECT COUNT(*)
FROM emp;
```

## Example #5 (COUNT)
Returns the count(number of occurrences) of salary (sal). (i.e. 14 salaries are in table, therefore the COUNT function returns 14)
```sql
SELECT COUNT(Sal)
FROM emp;
```

## Example #6 (COUNT)
Returns the count(number of occurrences) of commission (comm). This only returns 4, since there are only 4 values in comm. Basically, the COUNT function does not count NULL values. 
```sql
SELECT COUNT(comm)
FROM emp;
```

## Problem #1 
Write a query that returns the amount we pay to the highest paid manager in our company
```sql
SELECT MAX(sal)
FROM emp
WHERE job = 'MANAGER';
```

## Problem #1 (ver. 2)
Write a query that returns the amount we pay to the highest paid manager in our company
```sql
SELECT MAX(sal)
FROM emp
WHERE LOWER(job) like 'manager%';
```

## Example #7 
Compute average using the SUM and COUNT functions.
```sql
SELECT SUM(sal)/COUNT(*) AS "Computed Average"
FROM emp;
```

## Example #8 (mini report on everyone)
```sql
SELECT SUM(sal) AS TOTAL_SUM, AVG(SAL) as AVERAGE, MAX(sal) as MAXIMUM, MIN(sal) as MIN
FROM emp;
```

## Example #9 (mini report on just "MANAGERs")
```sql
SELECT SUM(sal) AS TOTAL_SUM, AVG(SAL) as AVERAGE, MAX(sal) as MAXIMUM, MIN(sal) as MIN
FROM emp;
WHERE job = 'MANAGER'
```

