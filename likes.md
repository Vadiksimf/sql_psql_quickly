## Real-world app practices

### Likes & posts
- Must be a separate table for likes;
- Add UNIQUE constrains: UNIQUE(user_id, post_id);
- Add type for like or posts

### EXAMPLE 1
#### Likes Table
For each type of likes we create a different table
| like_id | user_id | post_id | reaction_type| timestamp           |
|---------|---------|---------|-----------|---------------------|
| 1       | 123     | 456     | good      | 2023-11-13 12:00:00 |
| 2       | 789     | 123     | bad      | 2023-11-13 12:05:00 |
| 3       | 456     | 789     | wow      | 2023-11-13 12:10:00 |
| ...     | ...     | ...     | ...       | ...                 |


### EXAMPLE 2 - POLYMORPHIC ASSOCIATION (posts and comment table)
#### Likes Table
| like_id | user_id | like_id | liked_type| timestamp           |
|---------|---------|---------|-----------|---------------------|
| 1       | 123     | 456     | comment      | 2023-11-13 12:00:00 |
| 2       | 789     | 123     | post      | 2023-11-13 12:05:00 |
| 3       | 456     | 789     | comment      | 2023-11-13 12:10:00 |
| ...     | ...     | ...     | ...       | ...                 |

### EXAMPLE 3
#### Likes Table
| like_id | user_id | post_id | comments_id| timestamp           |
|---------|---------|---------|-----------|---------------------|
| 1       | 123     | 456     | NULL      | 2023-11-13 12:00:00 |
| 2       | 789     | NULL     | 123      | 2023-11-13 12:05:00 |
| 3       | 456     | 789     | NULL      | 2023-11-13 12:10:00 |
| ...     | ...     | ...     | ...       | ...                 |

add CHECK Validation:
ADD CHECK of
```sql
(
  COALESCE((post_id)::BOOLEAN::INTEGER, 0)
  +
  COALESCE((comment_id)::BOOLEAN::INTEGER, 0)
) = 1
```
