# INNER & OUTER JOINS

## Notes
* INNER JOIN: joins table on common values. If no common values found, then those row values will not be queried.
* LEFT JOIN: joins all values from the LEFT table regardless of matching values from the other table(s).
* RIGHT JOIN: joins all values from the RIGHT table regardless of matching values from the other table(s).
* FULL OUTER JOIN: joins all values from both tables, even if there is no matching criteria to join on. NULLs may appear from both sides...
* OUTER JOIN OPERATOR = (+) ,only oracle specific...not recommended for use


## Example #1 (INNER JOIN)
```sql
SELECT *
FROM emp e INNER JOIN dept d
ON e.deptno = d.deptno;
```

## Example #2 (RIGHTJOIN)
Gives me all data on the right table, which is the dept table in this case, regardless of whether there is a match in the other table.
```sql
SELECT *
FROM emp e RIGHT JOIN dept d
ON e.deptno = d.deptno;
```

## Example #3 (LEFT JOIN)
Gives me all data on the left table, which is the emp table in this case, regardless of whether there is a match in the other table.
```sql
SELECT *
FROM emp e LEFT JOIN dept d
ON e.deptno = d.deptno
```

## Example #4 (FULL OUTER JOIN)
The FULL OUTER JOIN joins all values from both tables, even if there is no matching criteria to join on. NULLs may appear from both sides...
```sql
SELECT *
FROM emp e FULL OUTER JOIN dept d
ON e.deptno = d.deptno
```

## Example #5  (subqueries and FULL OUTER JOIN)
There's more flexibility...but there's a performance cost. The subqueries __(SELECT * FROM emp)__ and __(SELECT * FROM dept)__ will run first and then the rest of the query. So calling tables directly like __FROM emp e, dept d__ is faster than subqueries.
```sql
SELECT *
FROM (SELECT * FROM emp) e FULL OUTER JOIN (SELECT * FROM dept) d
ON e.deptno = d.deptno
```

## Example #6 
```sql
SELECT *
FROM (SELECT * FROM emp WHERE job = 'SALESMAN') e FULL OUTER JOIN (SELECT * FROM dept) d
ON e.deptno = d.deptno
```