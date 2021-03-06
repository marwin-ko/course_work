# SQL Notes

[MySQL notes from techonthenet.com](https://www.techonthenet.com/mysql/index.php)

```sql
SELECT <column(s)>
FROM <table>
WHERE <single row functions or basic operations>
GROUP BY <column(s)>
HAVING <grouping functions or basic operations>
ORDER BY <column(s)>
```

- SQL is a case-insensitive language (except when calling strings).
- the * is used as wildcard
- add semicolon to the end of each statement
- use single quotes (''), for calling textual data from table(s).
- use single quotes (''), for making strings (for like concatenation)
= use ||, as known as pipes, to concatenate strings to data.
- use double quotes (""), for alias designation (column labeling)
- __!=__ is equivalent to <> for numerical data (e.g. sal!=3000 __~__ sal<>3000) 
- try to keep conditions together by keeping AND clauses together or separating by parenthesis.
- use -- to comment out lines
- You can use grouping functions in the HAVING clause. NOTE: WHERE clause is only for single row functions


## ERRORS
* too many values ==> misusing the IN clause (possible solution: use equals sign(=) instead of IN clause.

* single-row subquery returns more than one row ==> misusing the equals sign(=) (possible solution: use IN clause instead of equals sign(=))


## What is going on in the backend?
Given the following SQL statement. What is going on?
```sql
SELECT colA, colB
FROM tableA
WHERE colX = 3000
```
1. The interpreter (SQL software) looks at the FROM clause and is going to grab/load tableA in cache/memory.
2. The interpreter will now look at the WHERE clause and is going to eliminate the rows of data that do not equal 3000.
3. The interpreter will finally look at the SELECT clause and is going to eliminate all columns not selected. 
4. Final table is loaded.


## General Format A
```sql
```

## Example #1
```sql
```


__Operators__: >, <, >=, <=, =, !=