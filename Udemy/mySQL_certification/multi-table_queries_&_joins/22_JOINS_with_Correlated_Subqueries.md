# JOINs with Correlated Subqueries

## Notes
* NOT EXISTS and EXISTS are subquery support conditions
* NOT EXISTS and EXISTS are used in conjunction with subqueries
* NOT EXISTS and EXISTS are very inefficient (i.e. checks each row/record to determine if condition is met)
* NOT EXISTS and EXISTS are efficiently used for "correlated subquery". 


## Example #1 (setting same name aliases to keep query simple)
```sql
SELECT empno, ename, job, mgr, hiredate, sal, comm, e.deptno as deptno, d.deptno as deptno
FROM (SELECT * FROM dept) d LEFT OUTER JOIN (SELECT * FROM emp WHERE job = 'SALESMAN') e
ON e.deptno = d.deptno
```

## Example #2 (query all column shortcut)
Use table\_alias.* to call all columns from table\_alias.
```sql
SELECT e.*, d.*
FROM emp e, dept d;
```

## Example #3 (EXISTS)
EXISTS is used in conjunction with subqueries. This query returns nothing since subquery is false. NOTE: EXISTS is not efficient! It runs through all rows to determine if condition is satisified.
```sql
SELECT *
FROM emp
WHERE EXISTS(SELECT * FROM emp WHERE job = 'PROGRAMMER')
```

## Example #4 (NOT EXISTS)
NOT EXISTS is used in conjunction with subqueries. This query returns all rows from emp table since subquery is false. NOTE: NOT EXISTS is not efficient! It runs through all rows to determine if condition is satisified.
```sql
SELECT *
FROM emp
WHERE NOT EXISTS(SELECT * FROM emp WHERE job = 'PROGRAMMER')
```

## Example #5 (correlated subquery)
This query is checking for those departments it wants to print out and prints out those departments that EXISTS in the employee table. 
```sql
SELECT d.*
FROM dept d
WHERE EXISTS (SELECT * FROM emp WHERE d.deptno = emp.deptno)
```

## Example #6 (correlated subquery)
This query is checking for those departments it wants to print out and prints out those departments that do NOT EXISTS in the employee table.
```sql
SELECT d.*
FROM dept d
WHERE NOT EXISTS (SELECT * FROM emp WHERE d.deptno = emp.deptno)
```

## Example #7 (correlated subquery)
This query is checking for those departments it wants to print out and prints out those departments that do NOT EXISTS in the employee table OR if location is 'CHICAGO'.
```sql
SELECT d.*
FROM dept d
WHERE NOT EXISTS (SELECT * FROM emp WHERE d.deptno = emp.deptno)
OR loc = 'CHICAGO';
```

