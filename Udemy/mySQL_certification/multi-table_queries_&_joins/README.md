# Multi-Table Queries & Joins

## ERRORS
* too many values ==> misusing the IN clause (possible solution: use equals sign(=) instead of IN clause.

* single-row subquery returns more than one row ==> misusing the equals sign(=) (possible solution: use IN clause instead of equals sign(=))


## Subqueries 
* the nested portion in sequel is the first thing that gets run.
* similar to math, sequel will run the statements in parenthesis first.
* If the subquery returns multiple values, you will need to use the IN clause
* If the subquery returns a single value, you will need to use the equals sign (=)
* A subquery in the SELECT clause will need to be a single row query (scalar or single value). 


* table prefixes are necessary when a column name is not unique



## Example #
```sql
SELECT
FROM
WHERE NOT EXISTS (subquery)
```

## Example #
```sql
SELECT
FROM
```
