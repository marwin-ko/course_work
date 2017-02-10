# Creating Your Own Tables & Design Considerations

## NOTES
* Each table must have a __Primary Key__ column.
* __Primary Key__ column is a _unique identifier_ for every single record (row) in each table.
* Keep in mind how to use a __Primary Key__ to organize and connect tables. (e.g. The emp table uses an employee number as a Primary Key and the dept table uses deptartment number as a Primary Key. Both tables are connected by the department number!)
* [Click here for data types!](https://www.techonthenet.com/mysql/datatypes.php)

## Template!
```sql
CREATE TABLE table_name
(
col_ID number not null,
col_1 varchar(50),
...
col_n number 
);
```

## Example #1 (CREATE TABLE)
```sql
CREATE TABLE stores
(
store_id number not null,
city varchar(50)
);
```