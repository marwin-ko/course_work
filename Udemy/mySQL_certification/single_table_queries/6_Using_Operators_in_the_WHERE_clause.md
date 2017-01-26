# Using Operators in the __WHERE__ clause

## Example #1
Select/query all columns from employee(emp) table where _column job_ is not 'SALESMAN'. Basically, query data for everyone except for the salesmen.
```sql
SELECT *
FROM emp
WHERE job != 'SALESMAN';
```

## Example #2
Select/query all columns from employee(emp) table where _column job_ is not 'SALESMAN' and salary(sal) is less than or equal to 2500.
```sql
SELECT *
FROM emp
WHERE job != 'SALESMAN'
AND sal <= 2500;
```

## Problem #1
Write a query that returns those employees who have a commission greater than their salary.
```sql
SELECT *
FROM emp
WHERE comm > sal;
```

## Problem #2
Get all employees that are not managers and have a salary greater than 2500 and also work in department #20.
```sql
SELECT ename
FROM emp
WHERE job != 'MANAGER'
AND sal > 2500
AND deptno = 20;
```