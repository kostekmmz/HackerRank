Problem info:

https://www.hackerrank.com/challenges/the-company/problem?isFullScreen=true

````sql
SELECT DISTINCT c.company_code, 
c.founder,
count(distinct lm.lead_manager_code) as total_number_of_LM,
count(distinct sm.senior_manager_code) as total_number_of_SM,
count(distinct m.manager_code) as total_number_of_M,
count(distinct e.employee_code) as total_number_of_E
FROM Company c 
JOIN lead_manager lm ON  lm.company_code = c.company_code
JOIN senior_manager sm ON lm.lead_manager_code = sm.lead_manager_code
JOIN manager m ON sm.senior_manager_code = m.senior_manager_code
JOIN employee e ON e.manager_code = m.manager_code
group by c.company_code, c.founder
order by c.company_code asc
````
