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
