Problem info:

[PROBLEM - HackerRank](https://www.hackerrank.com/challenges/full-score/problem?isFullScreen=true)

**Solution:**
````sql
SELECT 
s.hacker_id,
h.name
FROM submissions s
JOIN challenges c ON c.challenge_id = s.challenge_id
JOIN difficulty d ON d.difficulty_level = c.difficulty_level
JOIN hackers h ON h.hacker_id = s.hacker_id
WHERE d.score = s.score
group by s.hacker_id, h.name
having count(s.hacker_id) >= 2 
order by count(s.hacker_id) desc, hacker_id asc
````
