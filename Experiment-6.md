# SQL LAB - EXPERIMENT 6
## AIM:- 
To perform SQL operations using date functions, formatting functions, and conditional expressions (DECODE) on the EMPLOYEE table.
## 1. Display empno, ename, deptno from employee table. Instead  of display department numbers display the related department name (Use decode function). 
```sql
SELECT empno, ename,
CASE deptno WHEN 10 THEN 'RESEARCH' WHEN 20 THEN 'ACCOUNTING' WHEN 30 THEN 'SALES' WHEN 40 THEN 'OPERATIONS' END AS deptno FROM employee;
```
# Output
| empno | ename  | deptno     |
|-------|--------|------------|
| 7369  | SMITH  | ACCOUNTING |
| 7499  | ALLEN  | SALES      |
| 7521  | WARD   | SALES      |
| 7566  | JONES  | ACCOUNTING |
| 7654  | MARTIN | SALES      |
| 7698  | BLAKE  | SALES      |
| 7782  | CLARK  | ACCOUNTING |
| 7788  | SCOTT  | OPERATIONS |
| 7839  | KING   | ACCOUNTING |
| 7844  | TURNER | SALES      |
| 7876  | ADAMS  | ACCOUNTING |
| 7900  | JAMES  | SALES      |
| 7902  | FORD   | ACCOUNTING | 
| 7934  | MILLER | RESEARCH   |

## 2. Display your age in days. 
```sql
SELECT DATEDIFF(CURDATE(), "2005-12-30") AS age_in_days;
```
# Output
| age_in_days |
|-------------|
|      7356   |

## 3. Display your age in months. 
```sql
SELECT TIMESTAMPDIFF(MONTH, "2005-12-30", CURDATE()) AS age_in_months;
```
# Output
| age_in_months |
|---------------|
|           241 |

## 4. Display the current date as 15th August Friday Nineteen Ninety-Seven. 
```sql
SELECT DATE_FORMAT(CURDATE(), "%D %M %W %Y") AS current_date_format;
```
# Output
| current_date_format       |
|---------------------------|
| 20th February Friday 2026 |

## 5. Display the following output for each row from employee table:- * Scott has joined the company on wednesday 13th August Nineteen Ninety.
```sql
SELECT CONCAT(ename, ' has joined the company on', DATE_FORMAT(hiredate, '%W %D %M %Y') AS message FROM employee;
```
# Output
| message                                                       |
|---------------------------------------------------------------|
| SMITH has joined the company on Wednesday 17th December 1980  |
| ALLEN has joined the company on Friday 20th February 1981     |
| WARD has joined the company on Sunday 22nd February 1981      |
| JONES has joined the company on Thursday 2nd April 1981       |
| MARTIN has joined the company on Monday 28th September 1981   |
| BLAKE has joined the company on Friday 1st May 1981           |
| CLARK has joined the company on Wednesday 9th June 1981       |
| SCOTT has joined the company on Thursday 9th December 1982    |
| KING has joined the company on Wednesday 17th November 1981   |
| TURNER has joined the company on Wednesday 8th September 1981 |
| ADAMS has joined the company on Wednesday 12th December 1983  |
| JAMES has joined the company on Thursday 3rd December 1981    |
| FORD has joined the company on Thursday 3rd December 1981     |
| MILLER has joined the company on Saturday 23rd January 1982   |

## 6. Find the date for nearest saturday after current date.
```sql
SELECT DATE_ADD (CURDATE(), INTERVAL(5 - WEEKDAY (CURDATE()) + 7) % 7 day) AS next_saturday;
```
# Output
| next_saturday |
|---------------|
| 2026-02-28    |

## 7. Display current time. 
```sql
SELECT CURTIME();
```
# Output
| CURTIME() |
|-----------|
| 00:26:11  |

## 8. Display the date three months Before the current date 
```sql
SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH) AS three_months_before;
```
# Output
| three_months_before |
|---------------------|
| 2025-11-20          |

## 9. Display those employees who joined in the company in the month of Dec. 
```sql
SELECT * 
FROM employee
WHERE MONTH(hiredate) = 12;
```
# Output
| empno | ename | job     | mgr  | hiredate   | sal  | comm | deptno |
|-------|-------|---------|------|------------|------|------|--------|
| 7369  | SMITH | CLERK   | 7902 | 1980-12-17 | 880  | NULL |     20 | 
| 7788  | SCOTT | ANALYST | 7566 | 1982-12-09 | 3300 | NULL |     40 |
| 7900  | JAMES | CLERK   | 7698 | 1981-12-03 | 1045 | NULL |     30 |
| 7902  | FORD  | ANALYST | 7566 | 1981-12-03 | 3300 | NULL |     20 
|
## 10. Display those employees whose first 2 characters from hire date -last 2 characters of salary. 
```sql
SELECT * FROM employee WHERE LEFT(YEAR (hiredate),2)=RIGHT(sal,2);
```
# Output
Empty Set

## 11. Display those employees whose 10% of salary is equal to the year of joining. 

## 12. Display those employees who joined the company before 15 of the months. 
## 13. Display those employees who has joined before 15th of the month 
## 14. Display those employees whose joining DATE is available in deptno 
