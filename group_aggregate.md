# GROUPPING AND AGREGATES

## Basic aggregates
```sql
select MAX(id)
from commentaries;

select MIN(id)
from users;

select COUNT(id)
from users;

select AVG(id)
from users;

select SUM(id)
from users;

select user_id, COUNT(id) as num_of_comments 
from commentaries
group by user_id;
```

## MORE COMPLEX aggregates
### FILTER AND COUNT
```sql
select status , COUNT(*)
from matches m 
group by status;

select "fixtureId", COUNT (*)
from events
where "fixtureId" = 1005897
group by "fixtureId";

select m."fixtureId", COUNT(*)
from events e 
join matches m on e."fixtureId" = m."fixtureId" 
GROUP BY m."fixtureId";

select m."fixtureId", "type", COUNT(*) as goals
from events e 
join matches m on e."fixtureId" = m."fixtureId"
where "type" = 'Goal'
group by m."fixtureId", "type"
having COUNT(*) > 4;

-- Find matches where average minute of GOALS was in 1 period
select "fixtureId", "type", AVG(cast(elapsed as int))
from events e
where "type" = 'Goal'
group by "fixtureId", "type"
having  AVG(cast(elapsed as int)) < 45;
```
