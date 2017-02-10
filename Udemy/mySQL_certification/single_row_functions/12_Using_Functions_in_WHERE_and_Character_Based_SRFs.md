# Using Functions in __WHERE__ And Character Based SRFs
Using functions in __WHERE__ clause for filtering purposes.

## Example #1 
```sql
SELECT *
FROM emp
WHERE LOWER(ename) = 'martin';
```

## Example # 2
```sql
SELECT *
FROM emp
WHERE job = UPPER('manager');
```

## Example # 3 (INITCAP)
```sql
SELECT INITCAP('hello my name is marwin') as "Introduction"
FROM dual;
```

## Example #4 (LENGTH)
```sql
SELECT ename, LENGTH(ename) as length
FROM emp
WHERE LENGTH(ename) = 6;
```

## Example #5 (SUBSTR)
You can use this function like SUBSTR('string_arg',start_index, num_chars). Note: 0 or 1 is the same for start_index. Also, num_chars includes the start index character. __OUTPUT: hel__.
```sql
SELECT SUBSTR('hello',1,3)
FROM dual;
```

## Example #6 (LPAD)
__OUTPUT: $$$DAY__
```sql
SELECT LPAD('Day',6, '$')
FROM dual;
```

## Example #7 (RPAD)
__OUTPUT: DAY$$$__
```sql
SELECT RPAD('Day',6, '$')
FROM dual;
```

## Example #8 (LTRIM)
__OUTPUT: ello__
```sql
SELECT LTRIM('hello','h')
FROM dual;
```

## Example #9 (LTRIM)
__OUTPUT: ello__
```sql
SELECT LTRIM('hhhhhhhhello','h')
FROM dual;
```