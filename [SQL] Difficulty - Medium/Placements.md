Problem info:

[PROBLEM - HackerRank](https://www.hackerrank.com/challenges/placements/)

````sql

WITH friend 
as(
(select salary, f.id, name
from students s 
join friends f on f.id = s.id
join packages p on p.id = f.friend_id) 
),
stud as
(
select s.id, salary, name
from students s 
join friends f on f.id = s.id
join packages p on p.id =f.id
)
select stud.name
from stud 
JOIN friend ON friend.id = stud.id
where friend.salary > stud.salary
order by friend.salary
````
