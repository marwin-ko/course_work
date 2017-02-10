# Numeric & Date Data type SRFs

## Example #1 (ROUND)
__OUTPUT: 107.03__
```sql
SELECT ROUND(107.029444,2)
FROM dual;
```

## Example #2 (TRUNC)
__OUTPUT: 107__
```sql
SELECT TRUNC(107.029444)
FROM dual;
```

## Example #3 (TRUNC)
__OUTPUT: 107.02__
```sql
SELECT TRUNC(107.029444,2)
FROM dual;
```

## Example #4 (SYSDATE)
The SYSDATE returns the current date that is set on the operating system of this particular database. __OUTPUT: 01/27/2017__
```sql
SELECT SYSDATE
FROM dual;
```

## Example #5 (SYSTIMESTAMP)
The SYSTIMESTAMP returns the date(day-month-year), time stamp(hr.min.sec.frac_sec XM), time zone. __OUTPUT: 27-JAN-17 10.47.07.384771 PM +00:00__
```sql
SELECT SYSTIMESTAMP
FROM dual;
```


## Example #6 (ADD_MONTHS)
__OUTPUT: 11/25/2017__
```sql
SELECT ADD_MONTHS('9/25/2017',2)
FROM dual;
```

## Example #7 ( ADD_MONTHS) 
The date was 1/27/17 when I ran this script. __OUTPUT: 04/27/2017__
```sql
SELECT ADD_MONTHS(SYSDATE, 3)
FROM dual;
```

## Example #8 ( ADD_MONTHS) 
The date was 1/27/16 when I ran this script. __OUTPUT: 10/27/2017__
```sql
SELECT ADD_MONTHS(SYSDATE, -3)
FROM dual;
```

## Example #9 (MONTHS_BETWEEN)
The MONTHS_BETWEEN() takes two dates and calculates the months between. The first argument is subtracted by the second argument. __OUTPUT: -11.645161290322580645161290322580645161__
```sql
SELECT MONTHS_BETWEEN('12/15/2012','12/4/2013')
FROM dual;
```

## Example #10 (MONTHS_BETWEEN)
 __OUTPUT: 12__
```sql
SELECT MONTHS_BETWEEN('12/4/2013','12/4/2012')
FROM dual;
```

## Example #11 (TRUNC)
Compare to example #5. TRUNC(date,'MONTH'). __OUTPUT: 01/27/2017__
```sql
SELECT TRUNC(SYSTIMESTAMP)
FROM dual;
```

## Example #12 (TRUNC)
Takes you to the "first" of the current month (aka changes day). 
__OUTPUT: 01/01/2017__
```sql
SELECT TRUNC(SYSTIMESTAMP,'MONTH')
FROM dual;
```

## Example #13 (TRUNC)
Takes you to the "first date of the the current year" (aka changes month and day). __OUTPUT: 01/01/2017__
```sql
SELECT TRUNC(SYSTIMESTAMP,'YEAR')
FROM dual;
```

## Example #14 (TRUNC)
Returns query of each hire date but "truncates" the day to the first of the month.
```sql
SELECT hiredate, TRUNC(hiredate, 'MONTH')
FROM emp;
```

## Example #15 (TRUNC)
Returns query of names where they were hired in 1982.
```sql
SELECT ename, TRUNC(hiredate,'MONTH')
FROM emp
WHERE TRUNC(hiredate,'YEAR') = '01/01/1982';
```