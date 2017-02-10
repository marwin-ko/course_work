# More Practice w/ __GROUP BY__ Clause

```sql
SELECT col_1, col_2, col_3, group_functions(aggregate_expression)
FROM tables
[ WHERE conditions]
GROUP BY col_1, col_2, col_3, ... col_n
[ ORDER BY conditions]
```
- In the SELECt clause, any other expressions that are not group functions (e.g. col\_1, col\_2...col\_n)  must also be in the GROUP BY clause.
- You can have multiple columns in the GROUP BY clause, but those columns do not necessarily have to be in the SELECT portion.

## Example #1 
This GROUP BY is creating a group from the combination of job and department number (deptno) and returns the COUNT of each group. So if all "managers" are from the same "department", then there is only one group for "managers". On the other hand, if "clerks" are from three different departments, then the "clerks" will be grouped into three different groups.
```sql
SELECT job, deptno, COUNT(*)
FROM emp
GROUP BY job, deptno
```