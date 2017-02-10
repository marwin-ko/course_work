# Views & Other Objects and Commands

## Notes
* __View__ is a named query. This is used to save complex queries.

## Template (creating a VIEW)
```sql
CREATE VIEW view_name AS 
<query>
```

## Template (edit VIEW object)
Add changes the query and run this command to edit/update VIEW object.
```sql
CREATE OR REPLACE VIEW view_name AS
<query>
```

## Example #1 (VIEW)
```sql
CREATE VIEW manager_v
AS SELECT * FROM employees
WHERE job = 'MANAGER'

--Use View
SELECT * FROM manager_v
```

## Example #2 (VIEW)
See all views in database.
```sql
SELECT * FROM user_objects
WHERE object_type = 'VIEW'
```

## Example #3
To look at the system details.
```sql
SELECT * FROM sys.V_$version
```

## Example #4 (DROP VIEW)
This drops the view.
```sql
DROP VIEW manager_v
```

## Project 
Write a query that gives me the record for the highest paid employee in each of the stores. Then create a VIEW for that query; so that we can call the VIEW for future uses.
```sql
CREATE VIEW super_employees_V AS 
SELECT e1.* FROM employees e1 
INNER JOIN 
  (SELECT store_id, max(sal) sal FROM employees GROUP BY store_id) e2
ON e1.store_id = e2.store_id
AND e1.sal = e2.sal
```

## Example #5 (UNION)
The UNION clause combines multiple tables. Note: Does not include duplicate records (unique values only!) and tables must have same columns (schema).
```sql
SELECT * FROM super_employees_V
UNION
SELECT * FROM employees
```

## Example #6 (UNION ALL)
The UNION ALL clause does the same thing as UNION, but now includes duplicate rows.
```sql
SELECT * FROM super_employees_V
UNION ALL
SELECT * FROM employees
```

## Example #7 (MINUS)
The MINUS clause subtracts the records that are mentioned below it from the top query. E.g. in this example, all the salesmen are removed from the table.
```sql
SELECT * FROM employees
MINUS
SELECT * FROM employees where job = 'SALESMAN'
```

## Example #8 (edit VIEW object)
```sql
CREATE OR REPLACE VIEW super_employees_V AS 
SELECT e1.* FROM employees e1 
INNER JOIN 
  (SELECT store_id, max(sal) sal FROM employees GROUP BY store_id) e2
ON e1.store_id = e2.store_id
AND e1.sal = e2.sal
```