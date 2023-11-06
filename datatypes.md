## Datatypes

## Numeric types
### No decimal
- SMALLING
- INTEGER
- BIGINT

### No decimal
- SMALLSERIAL
- SERIAL
- BIGSERIAL

### Decimal
#### Floating poins with good precise
- DECIMAL
- NUMERIC

#### Floating poins
- REAL
- DOUBLE PRECISION
- FLOAT

### Type convertations
Behave FLOAT as INTEGER
SELECT (2.0::INTEGER);

## Character types
- CHAR(5)      - length of characters always 5
- VARCHAR(50)  - from 1 to 50
- TEXT         - any length of string

## Boolean types
- TRUE (true, 'yes', 1, on, t, y)
- FALSE (false, 'no', 0, off, f, n)
- NONE

SELECE ('1'::BOOLEAN); # --> TRUE

## Date/time type
### DATE
- 'NOV-20-1980'::DATE

### TIME
- DATE
- TIME
- TIME WITH TIME ZONE
- TIMESTAMP WITH TIME ZONE

- '01:23 PM'::TIME  # --> TIME
- '01:23 PM EST'::TIME WITH TIME ZONE  # --> TIME in UTC

```sql
SELECT ('NOV 20 1988 1:23 AM EST'::TIMESTAMP WITH TIME ZONE)
-
       ('NOV 20 1987 1:23 AM EST'::TIMESTAMP WITH TIME ZONE);
# 0 years 0 mons 366 days 0 hours 0 mins 0.0 secs
```

### INTERVAL
- 1 day
- 1 D
- 1 D 1 M 1 S

```sql
SELECT ('NOV 20 1988 1:23 AM EST'::TIMESTAMP WITH TIME ZONE) -
('1 D'::INTERVAL);
```

#### We can make operations with intervals
SELECT

## Other types
- CURRENCY
- BINARY
- JSON
- GEOMETRIC
- RANGE
- ARRAYS
- BOOLEAN
- XML
- UUID

