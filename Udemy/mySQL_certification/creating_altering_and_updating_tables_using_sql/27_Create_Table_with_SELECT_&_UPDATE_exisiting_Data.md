# Create Table with __SELECT__ & __UPDATE__ existing Data


## Template (creating table from existing data)
```sql
CREATE TABLE new_table_name AS
SELECT col_1, col_2,...,col_n
FROM existing_table
```

## Template( UPDATING table)
```sql
UPDATE your_table
SET <column> = <value>
WHERE <some criteria>;
```

## Example #1 (creating table from existing data)
```sql
CREATE TABLE employees AS
SELECT empno, ename, job, hiredate, sal, comm
FROM emp;
```

## Example #2 (ADD columns to exisiting table)
Adds a (NULL value filled) column called store_id to the employees table.
```sql
ALTER TABLE employees
  ADD store_id number;
```

## Example #3 (UPDATE)
Updates the employee table and fills the entire store\_id column with 3. But you may not want that...so see example #4 for selectively updating.
```sql
UPDATE employees
SET store_id = 3;
```

## Example #4 
```sql
UPDATE employees
SET store_id = 3
WHERE ename in ('KING','BLAKE','Clark');

UPDATE employees
SET store_id = 2
WHERE job = 'SALESMAN';

UPDATE employees
SET store_id = 4
WHERE job in ('CLERK', 'ANALYSTS');

UPDATE employees
SET store_id = 1
WHERE ename = 'JONES';
```

## Example #5
Adding the NOT NULL modification to the store_id column.
```sql
ALTER TABLE employees
MODIFY store_id number NOT NULL;
```