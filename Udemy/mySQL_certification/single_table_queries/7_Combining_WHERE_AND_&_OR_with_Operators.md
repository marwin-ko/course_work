# Combining __WHERE__,__ AND__ & __OR__ with Operators

## Example #1
Incorrect query due to inaccurate logic! You cannot say that your job is 'CLERK' __AND__ 'SALESMAN', you can only have one job (from this table). A similar example of this inaccurate logic is like saying that your your birthday is on January 12th __AND__ May 30th...that just doesn't make sense.
```sql
SELECT *
FROM emp;
WHERE job = 'CLERK'
AND job = 'SALESMAN';
```

## Example #2
Correct version of example #1. Using __OR__ instead of __AND__.
```sql
SELECT  *
FROM emp
WHERE job = 'CLERK'
OR job = 'SALESMAN';
```

## Problem #1
Query the names of those employees that are not managers nor salesman and have a salary greater than or equal to 2000.
```sql
SELECT ename
FROM emp
WHERE job != 'MANAGER'
AND job != 'SALESMAN'
AND sal >= 2000;
```
Note: Important to use the __AND__ for job != 'MANAGER' and 'SALESMAN'. If __OR__ was used, then nothing would get filtered; the query would check for not 'MANAGER' __OR__ 'SALESMAN'. Meaning, if you look at job = "MANAGER", it would be queried since it is __not equal to__ "SALESMAN".


## Problem #2
Write a query to return the name and hire dates of those employees that work in Dallas or Chicago.
```sql
SELECT ename, hiredate
FROM emp
WHERE deptno = 20
OR deptno = 30;
```
NOTE: 20 and 30 are the department# (deptno) for Dallas and Chicago, respectively.


## Problem #2 (ver.2)
Same as above, but using __IN__ clause instead of __OR__ clause.
```sql
SELECT ename, hiredate
FROM emp
WHERE deptno IN (20,30);
```