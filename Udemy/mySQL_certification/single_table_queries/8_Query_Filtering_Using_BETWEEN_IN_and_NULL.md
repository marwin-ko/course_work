# Query Filtering Using __BETWEEN__, __IN__, and __NULL__

## __OR__ V.S. __IN__
Using __OR__ clause to query specific employee names. 
```sql
SELECT ename, hiredate
FROM emp
WHERE ename = 'ALLEN'
OR ename = 'WARD'
OR ename = 'FORD'
OR ename = 'SMITH';
```

Using __IN__ clause to query specific employee information. In this case, it is better to use the __IN__ clause as opposed to the __OR__ clause.
```sql
SELECT ename, hiredate
FROM emp
WHERE ename IN ('ALLEN','WARD','FORD','SMITH');
```

## Example #1
Query ename and hiredate for everyone except ('ALLEN','WARD','FORD','SMITH').
```sql
SELECT ename, hiredate
FROM emp
WHERE ename NOT IN ('ALLEN','WARD','FORD','SMITH');
```

## Example #2
```sql
SELECT *
FROM emp
WHERE hiredate BETWEEN '05/01/1981' AND '12/09/1982';
```

## Example #3
Returns data from employee table where commission(comm) is NULL. Null is empty. Note: (comm is NULL) is not the same as (comm = NULL)! DO NOT USE (col_name = NULL) ever! NULL is not equal to NULL....lol
```sql
SELECT *
FROM emp
WHERE comm is NULL;
```

## Problem #1
Write a query that returns those employees that have a salary between 1000 and 2000. Note: 1000 and 2000 are included in the range.
```sql
SELECT *
FROM emp
WHERE sal BETWEEN 1000 and 2000;
```

## Problem #1 (ver.2)
```sql
SELECT *
FROM emp
WHERE sal >= 1000 AND sal <= 2000;
```

## Problem #2
Write a query that returns employees that have a salary below 1000 or above 2000.
```sql
SELECT *
FROM emp
WHERE sal NOT BETWEEN 1000 and 2000;
```

## Problem #2 (ver.2)
Same as problem #2 above, but using operators instead of the BETWEEN clause.
```sql
SELECT *
FROM emp
WHERE sal < 1000 OR sal > 2000.
```

## Problem #3
Write a query that returns those employees that don't make any commission and have a salary greater than 1100 but less than 5000. Exclude those employees that have a salary equal to 3000. NOTE: __<>__ is equivalent to __!=__
```sql
SELECT *
FROM emp
WHERE (comm is NULL OR comm =0)
AND (sal > 1100 AND sal < 5000)
AND (sal <> 3000);
```



