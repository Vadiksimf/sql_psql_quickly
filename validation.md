## Validation

### is defined validation (NOT NULL, DEFAULT)
```sql
CREATE TABLE products (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  price INTEGER
);
```

```sql 
ALTER TABLE products
ALTER COLUMN price,
SET NOT NULL;
```

```sql
ALTER TABLE products
ALTER COLUMN price,
SET DEFAULT 0;
```

### is unique validation (UNIQUE)

#### Add
```sql
ALTER TABLE products
ADD UNIQUE (name);
```
#### only combination of name AND departments must be unique
```sql
ALTER TABLE products
ADD UNIQUE (name, department);
```

#### Remove
```sql
ALTER TABLE products
DROP CONSTRAINT products_name_key;
```

### custom validation - CHECK keyword
```sql
CREATE TABLE products (
  is SERIAL PRIMARY KEY,
  price INTEGER CHECK (price > 0),
);
```

```sql
ALTER TABLE products
ADD CHECK (price > 0);
```

```sql
CREATE TABLE orders (
  is SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  created_at TIMESTAMP NOT NULL,
  est_delivery TIMESTAMP NOT NULL,
  CHECK (created_at < est_delivery);
```

