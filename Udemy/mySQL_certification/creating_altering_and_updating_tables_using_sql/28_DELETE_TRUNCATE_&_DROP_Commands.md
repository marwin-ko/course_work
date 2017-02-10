# __DELETE__, __TRUNCATE__, & __DROP__ Commands

## Notes

## Error
* violated - child record found
    - cannot delete records that contain _Foreign Key Constraint_ (basically keys that are referred to from another table)
    
    
## Template
Drop the table constraint.
```sql
ALTER TABLE emp
  DROP CONSTRAINT <constraint name> 
```

## Template
Drops the table! GONE!
```sql
DROP TABLE <table_name>
```

## Template
Truncate deletes all data in the table. But does not delete the table itself.
```sql
TRUNCATE TABLE <table_name>
```

## Example #1 (DELETE)
Deletes records from dept table where deptno = 40. Basically, replace select with delete.
```sql
DELETE
FROM dept
WHERE deptno = 40;
```

## Example #2 (DROP)
Drops the _Foreign Key Constraint_ from the emp table. The __SYS\_C0054494303__ is the _Foreign Key Constraint_ for the deptno column in the emp table. 
```sql
ALTER TABLE emp
  DROP CONSTRAINT SYS_C0054494303 
```

## Example #3 (DROP)
Drop the table from database. It's gone!
```sql
DROP TABLE dept
```

## Example #4 (TRUNCATE)
Deletes all data in the table, but still preserves table object. However, the table is empty.
```sql
TRUNCATE TABLE emp
```