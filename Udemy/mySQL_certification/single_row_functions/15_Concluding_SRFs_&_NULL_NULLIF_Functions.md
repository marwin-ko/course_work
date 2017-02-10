# Concluding SRFs & NULL / NULLIF Functions


## Example #1 (NVL)
The NVL function replaces all null values in commission (comm) column with 0.
```sql
SELECT ename, job, sal, NVL(comm,0)
FROM emp
WHERE empno in (7839,7698,7566,7654);
```

## Example #2 (NVL)
The TO_CHAR function converts the commission (comm) into character/string type.
```sql
SELECT ename, job, sal, NVL(TO_CHAR(comm),'No Data Found')
FROM emp
WHERE empno in (7839,7698,7566,7654);
```

## Example #3 (NULLIF)
The NULLIF function takes two arguments and if both arguments are equal, then the NULLIF function returns a missing value or NULL value. In this case, if the length of the employee name (ename) is equal to 5, then the NULLIF function returns NULL.
```sql
SELECT ename, length(ename), NULLIF(length(ename),5) 
FROM emp;
```

## Problem #1
```sql
SELECT ename, length(ename), NVL(TO_CHAR(NULLIF(length(ename),5)),'Length equal to 5.')
FROM emp;
```

## Problem #1 (ver.2)
```sql
SELECT ename, length(ename), NVL(NULLIF(TO_CHAR(length(ename)),TO_CHAR(5)),'Length equal to 5.')
FROM emp;
```