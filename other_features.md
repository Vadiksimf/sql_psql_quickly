## DISTINCT keyword
- Gives all unique values inside of the column

```sql
# Gives unique combination department and name
SELECT DISTINCT department, name
FROM products;

# Count a number of unique departments
SELECT COUNT(DISTINCT department)
FROM products;
```

## GREATEST keyword
```sql
# Return the greatest value
SELECT name, weight, GREATEST(30, 2 * weight)
FROM products;
```

## CASE keyword
## GREATEST keyword
```sql
# Return the greatest value
SELECT name, price,
CASE
  WHEN price > 600 THEN 'high'
  WHEN price > 300 THEN 'medium'
  ELSE 'cheap'
  END
FROM products;
```
