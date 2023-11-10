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

### custom validation
