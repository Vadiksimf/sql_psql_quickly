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
)
UNION # shows only unique values -> removes dupclicates
# UNION ALL # doesn't removes duplicates
(
SELECT *
FROM products
ORDER BY price / weight DESC
);
```

### Using UNION
```sql
(
SELECT *
FROM products
ORDER BY price DESC
)
UNION # shows only unique values -> removes dupclicates
# UNION ALL # doesn't removes duplicates
(
SELECT *
FROM products
ORDER BY price / weight DESC
);
```

### Using INTERSECTION
```sql
(
SELECT *
FROM products
ORDER BY price DESC
)
INTERSECTION # shows only unique values which exist in query #1 and #2
# INTERSECTION ALL # doesn't removes duplicates
(
SELECT *
FROM products
ORDER BY price / weight DESC
);
```

### Using EXCEPTION
```sql
(
SELECT *
FROM products
ORDER BY price DESC
)
EXCEPTION # shows only unique values of query #1 which not in query #2
# EXCEPTION ALL # doesn't removes duplicates
(
SELECT *
FROM products
ORDER BY price / weight DESC
);
```

### Using SUBQUERIES
```sql
SELECT name, price
FROM orders
WHERE price > (
 SELECT MAX(price) FROM orders WHERE type = 'Toys'
);
```
