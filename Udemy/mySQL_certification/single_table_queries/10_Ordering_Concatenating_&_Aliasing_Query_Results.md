# Ordering, Concatenating & Aliasing Query Results

# Example #1 (aliasing)
Creates aliases/labels for columns. So ename becomes employee and sal becomes salary in the table being queried. Note: these aliases will be in all-caps. 
```sql
SELECT ename employee, sal salary, comm commission
FROM emp;
```

# Example #2 (aliasing)
Creates aliases for columns exactly as shown in quotes.
```sql
SELECT ename "Employee", sal "Salary", comm "Commission"
From emp;
```

# Example #3 (aliasing)
This is the __sequel standard__! Use this example for aliasing!
```sql
SELECT ename as "Employee", sal as "Salary", comm AS "Commission"
FROM emp;
```

# Example #4 (concatenating)
```sql
SELECT 'hello my name is ' || ename AS "concatenated value"
FROM emp;
where job = 'MANAGER'
```

# Problem #1 (concatenating)
Make a query that creates a report like below...  
```
King makes $5000 per month
Blake makes $2850 per month
Clark makes $2450 per month
```
```sql
SELECT ename || ' makes $' || sal || ' per month' AS "Employee Income"
FROM emp;
```

# Example #5 (ordering)
Returns query of employee table, ordered by salary. Default is a ascending (ASC) order (small to big). 
```sql
SELECT *
FROM emp
ORDER BY sal;
```

# Example #6 (ordering)
Returns query of employee table, ordered by salary in descending (DESC) order. 
```sql
SELECT *
FROM emp
ORDER BY sal DESC;
```

# Example #7 (ordering)
Return query of employee table, ordered by department#(deptno) first...then order by salary(sal). Think of it like "aggregating" by deptno first, then "organizing" by sal.
```sql
SELECT *
FROM emp
ORDER BY deptno, sal
```

# Example #8 (ordering)
Return query of employee table, ordered by department#(deptno) first...then order by salary(sal) where salary is in descending(DESC) order.
```sql
SELECT *
FROM emp
ORDER BY deptno, sal DESC
```




