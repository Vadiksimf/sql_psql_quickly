# SQL Arithmetic Operations

## Addition (`+`)
- Adds two numbers.
```sql
SELECT 5 + 3; -- Result: 8
```

## Subtraction (`-`)
- Subtracts the second number from the first.
```sql
SELECT 5 - 3; -- Result: 2
```

## Multiplication (`*`)
- Multiplies two numbers.
```sql
SELECT 5 * 3; -- Result: 15
```

## Division (`/`)
- Divides the first number by the second.
```sql
SELECT 6 / 3; -- Result: 2
```

## Modulus (`%`)
- Returns the remainder of the division of the first number by the second.
```sql
SELECT 5 % 3; -- Result: 2
```

## Example Usage in a Query

```sql
SELECT
    column1 + column2 AS addition,
    column1 - column2 AS subtraction,
    column1 * column2 AS multiplication,
    column1 / column2 AS division,
    column1 % column2 AS modulus
FROM
    table_name;
```
