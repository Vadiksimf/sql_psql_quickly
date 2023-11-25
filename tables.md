# Work with tables

```sql
# Create table
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
);
```

### INSERT data
```sql
INSERT INTO cities (name, country, population, area )
VALUES
  ('Tokyo', 'Japan', 38505000, 8223),
  ('Shanghai', 'China', 22125000, 5423);
```

### SELECT data
```sql
SELECT *
FROM cities LIMIT 10;
```

```sql
SELECT name, country
FROM cities;
```
```sql
SELECT name, population / area AS population_density
FROM cities;
```
```sql
SELECT name, price FROM phones
WHERE units_sold > 5000;
```
```sql
SELECT name, manufacturer
FROM phones
WHERE name = 'Apple';
```
```sql
SELECT name, manufacturer
FROM phones
WHERE name IN ('Apple', 'Nokia');
```
```sql
SELECT *
FROM cities
WHERE NOT IN (822, 8230) AND name = 'Tokyo';
```
```sql
SELECT name, manufacturer 
ROM phones
WHERE name = 'Apple' OR name = 'Nokia';
```
```sql
SELECT 
  name, 
  population # area AS population_density 
FROM 
  cities 
WHERE 
  population # area > 4000
```
  
### UPDATE and DELETE data
```sql
UPDATE cities
SET population = 39505000
WHERE name = 'Tokyo';
```
```sql
UPDATE cities
SET population = 555000
WHERE name = 'Shanghai' AND country = 'US';
```
### Remove all data
```sql
DELETE FROM cities;
WHERE "name" = 'Tokyo';
```

# DELETE TABLE
```sql
DROP TABLE photos;
```
