## SQL LAB - EXPERIMENT 7
## AIM:-
To perform various SQL queries on the EMPLOYEE table to retrieve aggregated data, apply conditions, and display results using functions like COUNT, SUM, MAX, MIN, GROUP BY, and date functions.
## 1. Compute the no. of days remaining in this year. 
```sql
SELECT DATEDIFF(CONCAT(YEAR(CURDATE()), '-12-31'), CURDATE()) AS days_remaining;
```
# Ouput
| days_remaining |
|----------------|
|            283 |

## 2. Find the highest and lowest salaries and the difference between of them. 
```sql
SELECT 
    MAX(sal) AS highest_salary,
    MIN(sal) AS lowest_salary,
    (MAX(sal) - MIN(sal)) AS difference
FROM employee;
```
# Output
| highest_salary | lowest_salary | difference |
|----------------|---------------|------------|
|          5500  |          880  |       4620 |

## 3. List employee whose commission is greater than 25 % of their salaries. 
```sql
SELECT ename, sal, comm
FROM employee 
WHERE comm > sal * 0.25 ;
```
# Output
| ename  | sal  | comm |
|--------|------|------|
| Martin | 1250 | 1400 |

## 4. Make a query that displays salary in dollar format. 
```sql
SELECT CONCAT('$', sal) AS D FROM employee;
```
## 5. Create a matrix query to display the job, the salary for that job based on department number, and the total salary for that job for all departments, giving each column an appropriate heading. 
## 6. Query that will display the total no of employees, and of that total the number who were hired in 1980,1981,1982 and 1983. Give appropriate column heading. 
## 7. Query to get the last Sunday of Any Month. 
## 8. Display department numbers and total number of employees working in each department. 
## 9. Display the various jobs and total number of employees within each job group. 
## 10. Display the depart numbers and total salary for each department. 
