## Examples with subquery in SELECT
Must be scalar queries
```sql
SELECT name, price, (
  SELECT price FROM products WHERE id = 3          # <--scalar query
) AS id_3_price
...
```

```sql
SELECT name, price, price / (
  SELECT MAX(price) FROM phones                    # <--scalar query
) AS price_ratio
FROM phones;
```

## Examples with subquery in FROM

1. Could be any queries. Must be only compatible with SELECT, WHERE, etc.
2. Must have an alias

```sql
SELECT name, price / weight AS price_weitht_ratio
FROM  (SELECT name, price / weight AS price_weight_ratio FROM products) AS p
WHERE price_weitht_ratio > 5;
```

#### Find the avetage number of orders for all users
```sql
SELECT AVG(o.order_count)
FROM (
  SELECT user_id, COUNT(*) as order_count
  FROM orders
  GROUP BY user _id
) as o;
```

#### Calculate average price of the phone for each manufacturers
```sql
SELECT manufacturer, MAX(p.avg_price)
FROM (
  SELECT manufacturer, AVG(price) as avg_price
  FROM phones
  GROUP_BY manufacturer
) AS p;
```

## Examples with subquery in JOIN
1. Could be any queries. Must be only compatible with 'ON' clause

```sql
SELECT first_name
FROM users
JOIN (
  SELECT user_id
  FROM ordres
  WHERE product_id = 3
) as o
ON o.user_id = users.id;
```

## Examples with subquery in WHERE

Query depends on the comparison operator (IN etc)
- IN / NOT IN: checks in a list of values
- >, =, <> ALL/SOME/ANY: returns single columnt
- SOME = ANY  ~ OR (single variant enouth)
- ALL         ~ AND (must match to all values)
```sql
SELECT id
FROM orders
WHERE product_id IN (
  SELECT id FROM products WHERE price / weight > 5
);
```

```sql
SELECT name, department
FROM priducts
WHERE department NOT IN (
  SELECT department FROM priducts WHERE price < 100
);
```

```sql
SELECT name, department, price
FROM priducts
WHERE department > ALL (
  SELECT price FROM priducts WHERE department = "Industrial"
);
```

```sql
SELECT name, price
FROM phones
WHERE price > (
  SELECT price FROM phones WHERE name = "Samsung S5629 Monte"
);
```

Select the name and price of phones which have price greater that price of any Samsung phone
```sql
SELECT name, price
FROM phones
WHERE price > ALL (SELECT price FROM phones WHERE manufacturer = 'Samsung');
```

## Corellated subquery 

```sql
SELECT name, depatment, price
FROM products AS p1
WHERE price = (SELECT MAX(price) FROM products AS p2 WHERE p2.department = p1.department);
```



