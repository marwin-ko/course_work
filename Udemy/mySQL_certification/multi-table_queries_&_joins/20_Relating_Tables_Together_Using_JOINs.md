# Relating Tables Together Using JOINs

Notes
* table prefixes are necessary when a column name is not unique

## Subquery VS JOINs
```sql
SELECT *
FROM emp
WHERE deptno = (SELECT deptno FROM dept WHERE loc='CHICAGO')
```

```sql
SELECT *
FROM emp, dept
WHERE emp.deptno = dept.deptno
```

## Example #1
Joining on emp table and dept table on deptno. 
```sql
SELECT *
FROM emp, dept
WHERE emp.deptno = dept.deptno
```

## Problem #1
Query the name, job title, and salary of employees that only work in Dallas. (Note: not all prefixes are necessary, only when column name is not unique.)
```sql
SELECT emp.ename, emp.job, emp.sal
FROM emp, dept
WHERE emp.deptno = dept.deptno
AND dept.loc = 'DALLAS'
```

## Example #2 (table alias)
```sql
SELECT e.ename, e.job, e.sal
FROM emp e, dept d
WHERE e.deptno = d.deptno
AND d.loc = 'DALLAS'
```


## Example #3 (table subquery)
This table subquery allows for more flexibility. You can filter out table data in subquery. See next example for more complex subquery. 
```sql
SELECT ename , job, sal
FROM (SELECT * from emp) e, dept d
WHERE e.deptno = d.deptno
```

## Example #4 (table subquery) 
```sql
SELECT ename , job, sal
FROM (SELECT * from emp WHERE job in ('MANAGER','CLERK')) e, dept d
WHERE e.deptno = d.deptno
```


## Problem #2 (table subquery)
Table subquery version of Problem #1. 
```sql
SELECT ename , job, sal
FROM emp e, (SELECT * FROM dept WHERE loc='DALLAS') d
WHERE e.deptno = d.deptno
```