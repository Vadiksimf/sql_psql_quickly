# sql_psql_quickly
Things to write SQL with Postgres

`sh
# Go to CLI
psql postgres

# Show databases
\dt+;

# Create table
CREATE TABLE cities ( name VARCHAR(50), country VARCHAR(50), population INTEGER, area INTEGER );

# INSERT data
INSERT INTO cities ( name, country, population, area ) VALUES ( 'Tokyo', 'Japan', 38505000, 8223), ( 'Shanghai', 'China', 22125000, 5423);

# SELECT data
SELECT * FROM cities LIMIT 10;
SELECT name, country FROM cities;
SELECT name, population / area AS population_density FROM cities;

SELECT name, price FROM phones WHERE units_sold > 5000;
SELECT name, manufacturer FROM phones WHERE name = 'Apple';

SELECT name, manufacturer FROM phones WHERE name IN ('Apple', 'Nokia');
SELECT name, manufacturer FROM phones WHERE name = 'Apple' OR name = 'Nokia';

SELECT 
  name, 
  population / area AS population_density 
FROM 
  cities 
WHERE 
  population / area > 4000
  
# UPDATE and DELETE data
UPDATE cities SET population = 39505000 WHERE name = 'Tokyo';
UPDATE cities SET population = 555000 WHERE name = 'Shanghai' AND country = 'US';
`
