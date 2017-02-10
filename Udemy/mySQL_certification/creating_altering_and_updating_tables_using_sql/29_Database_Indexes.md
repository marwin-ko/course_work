# Database Indices


## Notes
* Indices allow the computer to search for records faster.
* Creating indices for single or a combination of columns of a table _takes up space in the database_. Only create indices, if necessary.

## Template
If use [UNIQUE] clause, make sure that the column does not have duplicates. 
```sql
CREATE [UNIQUE] INDEX index_name
  ON table_name (col_1, col_2,...col_n)
  [COMPUTE STATISTICS]
```

## Example #1 (CREATE INDEX)
Creates index for the enames in the employees table. Now, the proceeding query is faster since the database is using the index to call the name. 
```sql
CREATE INDEX emp_name_idx
  ON employees (ename);

SELECT * FROM employees WHERE enmae = 'BLAKE';
```

## Example #2
Creates an index for the combination of ename, job, and hiredate. The __COMPUTE STATISTICS__ collects data on combination of the  ename, job, and hiredate columns and store statistics on those columns in the database. Oracle has an _optimizer_ that will optimize the query searches based on the statistics from __COMPUTE STATISTICS__.

```sql
CREATE INDEX emp_name_job_date_idx
ON employees (ename, job, hiredate)
COMPUTE STATISTICS

SELECT * FROM employees 
WHERE ename = 'BLAKE'
AND hiredate = 'MANAGER'
AND job = '05/01/1981'
```

## Example #3
Creates an index for only __UNIQUE__ column or columns. Note: this is example is useless since the empno is a Primary Key (unqiue key identifier); it's just purley an example.
```sql
CREATE UNIQUE INDEX empno_idx
ON employees (empno);
```

## Example #4 
Drops index that was created in example #1.
```sql
DROP INDEX emp_job_idx
```

## Example #5
If you forget to add the __COMPUTE STATISTICS__ when creating indices, then you can __ALTER__ the table like in this example.
```sql
ALTER INDEX emp_name_idx
REBUILD COMPUTE STATISTICS;
```