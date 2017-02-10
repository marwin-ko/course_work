# System Tables, Pseudo Columns & Deleting Duplicates

## Notes
* [Oracle System Notes](https://www.techonthenet.com/oracle/sys_tables/index.php)
* __SELECT__
    * __rowid__ is a pseudo column that all tables have.
* __FROM__
    * __all\_tables__ is a pseudo table (unique to oracle databases) that shows all tables in your database.
    * __all\_tab\_columns__ shows tables and their respective columns.
    * __all\objects__ shows all objects in database.
* __WHERE__
    * __table\_name__ is used to specify a table(s). (e.g. ```sql WHERE table_name = 'EMPLOYEES```)
    * __object\name__ is used to specify an object name.
    * __object\type__ is used to specify an object type.
    * __rownum__ is number of rows in a table
* 

## Project
Create a unique index on the store\_id column. Also, elect the store\_id column to be the Primary Key column.
```sql
-- Deletes Duplicate Records
DELETE FROM stores WHERE rowid NOT IN
(
SELECT MIN(rowid)
FROM stores
GROUP BY store_id, city
)
-- Make store_id a Primary Key.
ALTER TABLE stores
ADD CONSTRAINT storeid_pk PRIMARY KEY (store_id);

-- Try to add index to store_id column
-- The following command won't work because the previous command created an index via Primary Key constraint.
CREATE UNIQUE INDEX storeid_idx ON stores (store_id);
```

## Example #1 (all\_tables)
```sql
SELECT * FROM all_tables
```

## Example #2 (rownum)
```sql
SELECT * FROM all_tables
WHERE table_name = 'EMPLOYEES'
AND rownum < 10
```

## Example #3 (all\_tab\_columns)
```sql
SELECT * FROM all_tab_COLUMNS
WHERE table_name = 'EMPLOYEES'
```

## Example #4 (all\_objects)
```sql
SELECT * FROM all_objects
WHERE object_type = 'INDEX'
AND object_name = 'emp_name_idx'
AND rownum < 50
```

## Example #5 (SYNONYM)
Synonym creates a nick name or pointer for a table. Note: This may not be on the SQL certification exam.
```sql
CREATE PUBLIC SYNONYM emp_table
FOR employees

--Now we can call it as emp_table
SELECT * FROM emp_table
```
## Example #6 (rownum)
Can you rownum as column for sequential numbering.
```sql
SELECT rownum, enaume, sal FROM employees;
```