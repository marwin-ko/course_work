# __GROUP BY__ Clause & __HAVING__ Clause



## Example #1 
Returns the unique values of job. This is similar to the "SELECT DISTINCT job FROM emp", but remember that the GROUP BY function is actually still grouping by job. 
```sql
SELECT job
FROM emp
GROUP BY job
```

## Example #2
Returns average for each respective job "group" such as manager, clerk, and salesman.
```sql
SELECT job, AVG(sal)
FROM emp
GROUP BY job
```

## Example #3
Returns the number of occurrences of each job.
```sql
SELECT job, COUNT(*)
FROM emp
GROUP BY job
```

## Example #4 (HAVING)
You can use grouping functions in the HAVING clause. NOTE: WHERE clause is only for single row functions
```sql
SELECT job, AVG(sal), COUNT(*)
FROM emp
GROUP BY job
HAVING COUNT(*) = 2
```

## Problem #1
Write a query that returns those Department numbers that have more than three employees.
```sql
SELECT deptno, COUNT(*)
FROM emp
GROUP BY deptno
HAVING COUNT(*) > 3
```