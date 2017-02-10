# Alter Table & Modify Column Attributes


## Template (single modification)
```sql
ALTER TABLE table_name
  MODIFY col_name data_type(arg);
```

## Template (multiple modifications)
```sql
ALTER TABLE table_name
  MODIFY (col_name data_type(arg),
          col_name data_type(arg);
```

## Template (renaming columns)
```sql
ALTER TABLE table_name
  RENAME COLUMN col_name TO new_name,
```


## Example #1 (DESCRIBE)
Describes the products table. 
```sql
DESCRIBE products
```

## Example #2a (INSERT INTO)
```sql
INSERT INTO products VALUES (1011, '', 4.00, 8.00, 'Clothing', 3)
```

## Example #2b (DELETE)
We must delete the product_id = 1011, since the 2nd value, name, is NULL. We want to alter name column to exclude NULL values (aka NOT NULL).
```sql
DELETE FROM products WHERE product_id = 1011;
```

## Example #2c (ALTER TABLE, MODIFY)
```sql
ALTER TABLE products
  MODIFY name varchar2(50) not null
```

## Example #3 (ALTER TABLE, MODIFY)
Applying multiple modifications to the table.
```sql
ALTER TABLE products
  MODIFY (product_cost number(5,2) not null,
          product_retail number(5,2) not null);
```

## Example #4 (ALTER TABLE, RENAME)
Applying multiple modifications to the table.
```sql
ALTER TABLE products
  RENAME COLUMN name TO product_name; 
```