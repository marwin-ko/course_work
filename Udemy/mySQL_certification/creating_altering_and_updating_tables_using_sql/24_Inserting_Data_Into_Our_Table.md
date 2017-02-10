# Inserting Data Into Our Table

## Template
```sql
INSERT INTO table_name(col_ID, col_1,...,col_n) VALUES (num_ID, data point,..., col_n);
```

## Example #1  (INSERT INTO....VALUES)
```sql
INSERT INTO stores(store_id, city) VALUES(1, 'San Francisco');
INSERT INTO stores(store_id, city) VALUES(2, 'New York City');
INSERT INTO stores(city, store_id) VALUES('Merced', 3);
INSERT INTO stores(store_id, city) VALUES(4, 'Philadelphia');
```

## Example #2 (INSERT ALL.....)
```sql
INSERT ALL
    INTO stores (store_id, city) VALUES (5, 'Boston')
    INTO stores (store_id, city) VALUES (6, 'Seattle')
    INTO stores (store_id, city) VALUES (7, 'San Mateo')
SELECT * FROM DUAL;
```