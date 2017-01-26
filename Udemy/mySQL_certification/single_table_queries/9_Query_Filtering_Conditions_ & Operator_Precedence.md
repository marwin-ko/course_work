# Query Filtering Conditions & Operator Precedence

## Problem #1
Return those employees that are salesman and that make either 300 dollars in commission or greater than 1000 dollars in commission. 
```sql
SELECT *
FROM emp
WHERE (job = 'SALESMAN') AND (comm = 300 OR comm > 1000);
```

## Problem #1 (ver.2)
Using the LIKE clause instead of the equals sign (=). LIKE 'S%' is the LIKE clause taking a string that starts with 'S' and any proceeding letters after (aka wildcard, aka %).
```sql
SELECT *
FROM emp
WHERE (job LIKE 'S%') AND (comm = 300 OR comm > 1000);
```

## Problem #1 (ver.3)
Using the LIKE clause instead of the equals sign (=). LIKE '%MAN' is the LIKE clause taking any letters in a string that ends in 'MAN'. 
```sql
SELECT *
FROM emp
WHERE (job LIKE '%MAN') AND (comm = 300 OR comm > 1000);
```
