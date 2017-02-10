# SELECT within SELECT (Subqueries)

NOTES
* the nested portion in sequel is the first thing that gets run.
* similar to math, sequel will run the statements in parenthesis first.
* If the subquery returns multiple values, you will need to use the IN clause
* If the subquery returns a single value, you will need to use the equals sign (=)
* A subquery in the SELECT clause will need to be a single row query (scalar or single value). 

## Example #1 (subquery in WHERE)
The subquery __(SELECT deptno FROM dept WHERE deptno = 30)__ gets run first to obtain the value. Then the rest of the query runs as usual.
```sql
SELECT * FROM dept
WHERE deptno = (SELECT deptno FROM dept WHERE deptno = 30);
```


## Example #2 (subquery in FROM)
Grabing data from a subqueried data.
```sql
SELECT * 
FROM (SELECT * FROM emp);
```

## Example #3 (subqury in WHERE)
The subquery is grabing the department number(deptno)from the deptartment(dept) table where the location (loc) is 'Chicago'. This is essentially using the dept table to grab the deptno where the location is 'Chicago' and using that deptno to qery data from the emp table. Basically, we queried people in the department located Chicago in the emp table.
```sql
SELECT *
FROM emp
WHERE deptno = (SELECT deptno FROM dept WHERE loc = 'CHICAGO')
```

## Example #3 (subquery in WHERE)
If subquery returns multiple data point (list of data), then we need to use the IN clause!
```sql
SELECT *
FROM emp
WHERE deptno IN (SELECT deptno FROM dept WHERE deptno in (10,20))
```


## Example #4 (subquery in SELECT)
The query returns job, ename, and the the subquery. The Subquery returns King's job, which is 'PRESIDENT'. So President is repeat over and over in the subquery column. NOTE: The subquery in the SELECT clause will need to be a single row query. 
```sql
SELECT job, ename, (SELECT job FROM emp where ename = 'KING')
FROM emp
```