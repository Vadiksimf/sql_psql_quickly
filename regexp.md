# REGEXP

### Starts with
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU]';  # NOT STARTS WITH: WHERE city NOT REGEXP '^[aeiouAEIOU]';
```

### Ends with
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '[aeiouAEIOU]$';
```

### Simultaneously starts and ends with
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[aeiouAEIOU].*[aeiouAEIOU]$';
```

### Using substrings
```sql
SELECT name
FROM students
WHERE marks > 75
ORDER BY SUBSTRING(name, -3), id ASC; # THE SAME AS REGEXP_SUBSTR(NAME, '.{3}$')
```
