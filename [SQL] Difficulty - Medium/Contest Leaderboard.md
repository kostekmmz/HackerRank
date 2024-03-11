Problem info:

[PROBLEM - HackerRank](https://www.hackerrank.com/challenges/contest-leaderboard))

````sql
select 
a.hacker_id,
h.name,
sum(cc)
from (
select max(score) as cc,
s.hacker_id,
s.challenge_id
from submissions s 
group by s.challenge_id, s.hacker_id
) a 
JOIN hackers h ON h.hacker_id =  a.hacker_id
group by a.hacker_id, h.name
having sum(cc) <> 0 
order by sum(cc) desc, hacker_id asc
````
