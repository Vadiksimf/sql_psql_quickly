# Getting Unique Values in SQL

## Using `DISTINCT`

The `DISTINCT` keyword is used to return only distinct (different) values.

### Example

```sql
SELECT DISTINCT column_name
FROM table_name;
```

### Multiple Columns

You can also use `DISTINCT` with multiple columns.

```sql
SELECT DISTINCT column1, column2
FROM table_name;
```

## Using `GROUP BY`

The `GROUP BY` statement groups rows that have the same values into summary rows.

### Example

```sql
SELECT column_name
FROM table_name
GROUP BY column_name;
```

### Multiple Columns

You can group by multiple columns as well.

```sql
SELECT column1, column2
FROM table_name
GROUP BY column1, column2;
```

## Using `UNIQUE` Constraint

The `UNIQUE` constraint ensures that all values in a column are different. This is more of a table design consideration.

### Example

```sql
CREATE TABLE table_name (
    column_name datatype UNIQUE
);
```

## Using `ROW_NUMBER()` with Common Table Expressions (CTEs)

You can use the `ROW_NUMBER()` window function to assign a unique number to each row within a partition of a result set.

### Example

```sql
WITH CTE AS (
    SELECT column_name, ROW_NUMBER() OVER (PARTITION BY column_name ORDER BY column_name) AS row_num
    FROM table_name
)
SELECT column_name
FROM CTE
WHERE row_num = 1;
```

## Using `EXISTS`

You can use the `EXISTS` clause to filter out duplicate rows.

### Example

```sql
SELECT column_name
FROM table_name t1
WHERE EXISTS (
    SELECT 1
    FROM table_name t2
    WHERE t1.column_name = t2.column_name
    AND t1.id <= t2.id
);
```

## Using `DISTINCT ON` (PostgreSQL Specific)

In PostgreSQL, you can use `DISTINCT ON` to get unique rows based on specific columns.

### Example

```sql
SELECT DISTINCT ON (column_name) *
FROM table_name
ORDER BY column_name, another_column;
```
