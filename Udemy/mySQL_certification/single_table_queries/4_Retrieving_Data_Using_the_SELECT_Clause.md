# Retrieving Data Using the __SELECT__ Clause

## General Format
```sql
SELECT <column>
FROM <table>;
```

## Example #1
Select/query all columns(*) and rows from employee(emp) table.
```sql
SELECT *
FROM emp;
```

## Example #2
Select/query department names(dname) and location (loc) from department(dept) table.
```sql
SELECT dname, loc
FROM dept;
```

## Example #3
Select/query distinct/unique jobs from employee(emp) table.
```sql
SELECT DISTINCT job
FROM emp;
```