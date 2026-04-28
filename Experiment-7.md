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
# Output
| D     |
|-------|
| $800  |
| $1600 |
| $1250 |
| $3273 |
| $1250 |
| $3135 |
| $2965 |
| $3300 |
| $5500 |
| $1500 |
| $1210 |
| $1045 |
| $3300 |
| $1430 |

## 5. Create a matrix query to display the job, the salary for that job based on department number, and the total salary for that job for all departments, giving each column an appropriate heading. 
```sql
SELECT job,
SUM(CASE WHEN deptno = 10 THEN sal ELSE 0 END) AS Deptno10,
SUM(CASE WHEN deptno = 20 THEN sal ELSE 0 END) AS Deptno20,
SUM(CASE WHEN deptno = 30 THEN sal ELSE 0 END) AS Deptno30,
SUM(CASE WHEN deptno = 40 THEN sal ELSE 0 END) AS Deptno40,
SUM(sal) AS Total_sal
FROM employee
GROUP BY job;
```
# Output
| job       | Deptno10 | Deptno20 | Deptno30 | Deptno40 | Total_sal |
|-----------|----------|----------|----------|----------|-----------|
| CLERK     | 1430     | 2090     | 1045     | 0        | 4565      |
| SALESMAN  | 0        | 0        | 5600     | 0        | 5600      |
| MANAGER   | 0        | 5968     | 3135     | 0        | 9103      |
| ANALYST   | 0        | 3300     | 0        | 3300     | 6600      |
| PRESIDENT | 0        | 5500     | 0        | 0        | 5500      |

## 6. Query that will display the total no of employees, and of that total the number who were hired in 1980,1981,1982 and 1983. Give appropriate column heading. 
```sql
SELECT COUNT(*) AS total_emp,
SUM(CASE WHEN YEAR(hiredate)=1980 THEN 1 ELSE 0 END) AS Y1980,
SUM(CASE WHEN YEAR(hiredate)=1981 THEN 1 ELSE 0 END) AS Y1981,
SUM(CASE WHEN YEAR(hiredate)=1982 THEN 1 ELSE 0 END) AS Y1982,
SUM(CASE WHEN YEAR(hiredate)=1983 THEN 1 ELSE 0 END) AS Y1983,
 ename FROM employee;
```
# Output
| total_emp | Y1980 | Y1981 | Y1982 | Y1983 | ename |
|-----------|-------|-------|-------|-------|-------|
| 14        | 1     | 10    | 2     | 1     | SMITH |

## 7. Query to get the last Sunday of Any Month. 
```sql
SELECT DATE_SUB(
LAST_DAY(CURDATE()),
INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE())) - 1) DAY
) AS last_sunday;
```
# Output
| last_sunday |
|-------------|
| 2026-04-26  |

## 8. Display department numbers and total number of employees working in each department. 
```sql
SELECT deptno, COUNT(*) AS total_employees
FROM employee
GROUP BY deptno;
```
# Output
| deptno | total_employees |
|--------|-----------------|
| 10     | 1               |
| 20     | 6               |
| 30     | 6               |
| 40     | 1               |

## 9. Display the various jobs and total number of employees within each job group. 
```sql
SELECT job, COUNT(*) AS total_employees
FROM employee
GROUP BY job;
```
# Output
| job       | total_employees |
|-----------|----------------|
| CLERK     | 4              |
| SALESMAN  | 4              |
| MANAGER   | 3              |
| ANALYST   | 2              |
| PRESIDENT | 1              |

## 10. Display the depart numbers and total salary for each department. 
```sql
SELECT deptno, SUM(sal) AS total_salary
FROM employee
GROUP BY deptno;
```
# Output
| deptno | total_salary |
|--------|--------------|
| 10     | 1430         |
| 20     | 16858        |
| 30     | 9780         |
| 40     | 3300         |

