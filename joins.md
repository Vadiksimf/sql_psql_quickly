# Table connections. (PK/FK/JOIN)

```sql
# Primary key / Foreign key
CREATE TABLE users (
  # id SERIAL PRIMARY KEY,
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name VARCHAR(50)
);

CREATE TABLE photos (
  id SERIAL PRIMARY KEY,
  url VARCHAR (255),
  user_id INTEGER REFERENCES users(id) ON DELETE SET NULL
);

CREATE TABLE comments (
  id SERIAL PRIMARY KEY,
  text VARCHAR(255),
  user_id INTEGER REFERENCES users(is) ON DELETE SET NULL
);

# ON DELETE NO ACTION --> ERROR
# ON DELETE RESTRICT  --> ERROR
# ON DELETE CASCADE
# ON DELETE SET NULL
# ON DELETE SET DEFAULT

# JOINS
# Add all values from photos, such as id, url
SELECT comment, url
FROM comments
JOIN photos ON photos.id = comments.photo_id

# MULTIPLE JOINS AND FILTERING
select url, text, name
from users u
full join commentaries c on u.id = c.user_id
full join photos p on u.id = p.user_id and u.id = c.user_id;
```
