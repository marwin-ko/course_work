# Using the __WHERE__ Clause in a Query

## General Format A
```sql
SELECT <column>
FROM <table>
WHERE <column> = 'string'
```

## Example #1
Select/query all columns from employee(emp) table where _column job_ is equal to 'MANAGER'. Note: The string is a case sensitive.
```sql
SELECT *
FROM emp
WHERE job = 'MANAGER'
```

## Example #2 
Select/query all columns from employee(emp) table where _column job_ is equal to 'SALESMAN' and _column salary (sal)_ is equal to 1600.
```sql
SELECT *
FROM emp
WHERE job = 'SALESMAN'
AND sal = 1600
```

## Example #3
Select/query all columns from employee(emp) table where _column job_ is equal to 'SALESMAN' and _column salary (sal)_ is less than or equal to 1600 and _column commission(comm)_ is equal to 300.
```sql
SELECT *
FROM emp
WHERE job = 'SALESMAN'
AND sal <= 1600
AND comm = 300;
```


