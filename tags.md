# Tags

- Tags in a picture have x and y dimention
- Tags in text doesn't have it

  1. One table for tags
  
| tag_id | post_id | x_dimension | y_dimension |
|--------|---------|-------------|-------------|
| 1      | 201     |  20          | 30          |
| 2      | 202     |  null        | null        |
| 3      | 203     |  15          | 25          |


  2. Separate tables (photo_tags, caption_tags) <br>
Here we have more cases for optimization

| tag_id | post_id |  x_dimension | y_dimension |
|--------|---------|-------------|-------------|
| 1      | 201     |  20          | 30          |
| 3      | 203     |  15          | 25          |


| tag_id | post_id | 
|--------|---------|
| 2      | 202     |

