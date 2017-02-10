# Single Row Functions (SRF) & Using The Dual Table

## List of Single Row Functions
- CONCAT('text input or column','text input or column')
- UPPER('text input')
- LOWER('text input') 

## Example #1 (CONCAT)
Returns a query of each employee name where each row is 'my name is \<ename\>'.
```sql
SELECT CONCAT('my name is ', ename) as sentence
FROM emp;
```

## Example #2 (UPPER)
Returns the word, 'HELLO', n times for n rows. (i.e. if there are 10 employees, this query returns the word as 'HELLO' 10 times, once per row)
```sql
SELECT UPPER('hello')
FROM emp;
```

## Example #3 (nesting functions)
__Remember to use "" for column labeling!___
```sql
SELECT CONCAT(UPPER('hello '),ename) as "Introduction"
FROM emp;
```

## DUAL Table
The dual table has only one value. It's basically a dummy table that you use to test functionality. NOTE: This is Oracle mySQL specific, aka, may not be available in other sequel software.
```sql
SELECT *
FROM dual
```

## Example #4 (DUAL)
Adds columns and data into dual table.
```sql
SELECT 'pizza' AS Food, 'fanta' AS drink
FROM DUAL
```

## Problem #1 (nesting functions)
```sql
SELECT CONCAT(CONCAT(ename, UPPER('is the name')),CONCAT(' and their job is: ',job)) as "function call"
FROM emp;
```