# Single Row Functions (SRFs)

[List of SQL Functions!](https://www.techonthenet.com/oracle/functions/)

Types of SRFs: numeric, null, date

- UPPER(arg) 
- LOWER(arg)
- INITCAP(arg) ==> capitalizes the initial letter of every work in string 
- LENGTH(arg)
- CONCAT(arg1,arg2)
- SUBSTR('str_arg',start_index,num_characters)
- LPAD('str_arg',total_str_length,'pad_char') ==> adds characters to the left side of the str_arg.
- RPAD('str_arg',total_str_length,'pad_char') ==> adds characters to the right side of the str_arg.
- LTRIM('str_arg','trim_char') ==> trims str from left side
- RTRIM('str_arg','trim_char') ==> trims str from right side


- ROUND(float_num,n\_decimal_place) ==> rounds to the n decimal place
- TRUNC(float_num,n\_decimal_place) ==> removes n decimal places
- TRUNC(float_num) ==> removes all decinal places 
- TRUNC(date, 'MONTH or YEAR')
- SYSDATE ==> returns the current date that is set on the operating system of this particular database.
- SYSTIMESTAMP ==> returns the date(day-month-year), time stamp(hr.min.sec.frac_sec XM), time zone.
- ADD\_MONTHS()
- MONTHS\_BETWEEN()

- TO\_CHAR()
- TO\_DATE 
- NVL()
- NVL2()
- NULLIF(arg1,arg2) ==> The NULLIF function takes two arguments and if both arguments are equal, then the - NULLIF function returns a missing value or NULL value.