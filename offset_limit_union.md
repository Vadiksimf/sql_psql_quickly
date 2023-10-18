## Offset and limit

 ```sql
SELECT(*)
FROM users
LIMIT 999  # show 999 values 
OFFSET 50; # start from 50
```
### Using UNION
```sql
(
SELECT *
FROM products
ORDER BY price DESC
LIMIT
)
UNION # shows only unique values -> removes dupclicates
# UNION ALL # doesn't removes duplicates
(
SELECT *
FROM products
ORDER BY price / weight DESC
LIMIT 4
);
```
