Problem info:

[PROBLEM - HackerRank](https://www.hackerrank.com/challenges/binary-search-tree-1/problem?isFullScreen=true)

**Solution:**

````sql
SELECT 
distinct n
,case when P is null then 'Root'
when n in (select distinct p from bst) then 'Inner'
else 'Leaf'
end as 'info'
from bst
order by n asc
````
