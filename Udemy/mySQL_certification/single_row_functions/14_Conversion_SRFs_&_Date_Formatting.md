# Conversion SRFs & Date Formatting

TO_CHAR(sysdate, 'Month DD,YYYY')
    Result: January 29, 2017
    
TO_CHAR(123,'$999.99')
    Result: $123.00 
    
TO_DATE('str','fmt')
## Example #1 (TO\_CHAR)
__OUTPUT: 29-01-2017__
```sql
SELECT TO_CHAR(sysdate, 'dd-mm-yyyy')
FROM dual
```

## Example #2 (TO\_CHAR)
__OUTPUT: 01-29-2017__
```sql
SELECT TO_CHAR(sysdate, 'mm-dd-yyyy')
FROM dual
```

## Example #3 (TO\_CHAR)
__OUTPUT: 29th of january , 2017__
```sql
SELECT TO_CHAR(sysdate,'ddth "of" month, yyyy')
FROM dual
```

## Example #4 (TO\_CHAR)
```sql
SELECT TO_CHAR(sal, '$99,999.99') AS salary
FROM emp
```

## Example #5 (TO\_DATE)
__OUTPUT: 08/21/2012__
```sql
SELECT TO_DATE('2012-08-27','yyyy-mm-dd')
FROM dual
```

## Example #6 (TO\_DATE)
__OUTPUT: 10/21/2012__
```sql
SELECT ADD_MONTHS(TO_DATE('2012-08-27','yyyy-mm-dd'),2)
FROM dual
```

## Example #7 (TO\_DATE)
__OUTPUT: 06/03/2012__
```sql
SELECT TO_DATE('3 of June, 2012','dd "of" month, yyyy')
FROM dual
```