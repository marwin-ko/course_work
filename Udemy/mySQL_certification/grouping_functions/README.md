# Grouping Functions

NOTES
- Cannot (DO NOT!) use grouping functions in the WHERE clause (e.g. WHERE COUNT(*) = 2). Only single row functions are allowed in the WHERE clause.
- Use HAVING after GROUP BY clause to filter (e.g. GROUP BY job HAVING COUNT(*) = 2)

MIN()
MAX()
SUM()
AVG()
COUNT()


SELECT col_1, col_2, col_3, group_functions(aggregate_expression)
FROM tables
[ WHERE conditions]
GROUP BY col_1, col_2, col_3, ... col_n
[ ORDER BY conditions]