# SQL LAB - EXPERIMENT 5
## AIM:- 
To perform aggregate and string operations on the EMPLOYEE table using SQL functions such as COUNT, SUM, AVG, MAX, MIN, and string functions like UPPER, LOWER, LENGTH.
## 1. Display the total number of employee working in the company.
```sql
SELECT COUNT(*) AS total_employee_working FROM employee;
```
# Output
|total_employee_working |
|-----------------------|
|                    14 |

## 2. Display the total salary being paid to all employees. 
```sql
SELECT SUM(sal) AS total_salary_paid FROM employee;
```
# Output
| total_salary_paid |
|-------------------|
|             31368 |

## 3. Display the maximum salary from employee table.
```sql
SELECT MAX(sal) FROM employee;
```
# Output
| MAX(sal) |
|----------|
|   5500   |

## 4. Display the minimum salary from employee table. 
```sql
SELECT MIN(sal) FROM employee;
```
# Output
| MIN(sal) |
|----------|
|      880 |

## 5. Display the average salary from employee table 
```sql
SELECT AVG(sal) FROM employee;
```
# Output
| AVG(sal)  |
|-----------|
| 2240.5714 |

## 6. Display the maximum salary being paid to clerk. 
```sql
SELECT MAX(sal) 
FROM employee 
WHERE job = 'CLERK';
```
# Output
| MAX(sal) |
|----------|
|    1430  |

## 7. Display the maximum salary being paid in dept no 20. 
```sql
SELECT MAX(sal) 
FROM employee 
WHERE deptno = 20;
```
# Output
| MAX(sal) |
|----------|
|    5500  |

## 8. Display the minimum salary paid to any salesman. 
```sql
SELECT MIN(sal) 
FROM employee 
WHERE job = 'SALESMAN';
```
# Output
| MIN(sal) |
|----------|
|     1250 |

## 9. Display the average salary drawn by managers. 
```sql
SELECT AVG(sal) 
FROM employee 
WHERE job = 'MANAGER';
```
# Output
| AVG(sal)  |
|-----------|
| 3034.3333 |

## 10. Display the total salary drawn by analyst working in dept no 40. 
```sql
SELECT SUM(sal) 
FROM employee 
WHERE job = 'ANALYST' AND deptno = 40;
```
# Output
| SUM(sal) |
|----------|
|   3300   |

## 11. Display the names of the employee in Uppercase. 

```sql
SELECT UPPER(ename) FROM employee;
```
# Output
| UPPER(ename) |
|--------------|
| SMITH        |
| ALLEN        |
| WARD         |
| JONES        |
| MARTIN       |
| BLAKE        |
| CLARK        |
| SCOTT        |
| KING         |
| TURNER       |
| ADAMS        |
| JAMES        |
| FORD         |
| MILLER       |

## 12. Display the names of the employee in Lowercase. 
```sql
SELECT LOWER(ename) FROM employee;
```
# Output
| LOWER(ename) |
|--------------|
| smith        |
| allen        |
| ward         |
| jones        |
| martin       |
| blake        |
| clark        |
| scott        |
| king         |
| turner       |
| adams        |
| james        |
| ford         |
| miller       |

## 13. Display the names of the employee in Proper case. 
```sql
SELECT CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2))) FROM employee;
```
# Output
| CONCAT(UPPER(LEFT(ename,1)), LOWER(SUBSTRING(ename,2))) |
|---------------------------------------------------------|
| Smith                                                   |
| Allen                                                   |
| Ward                                                    |
| Jones                                                   |
| Martin                                                  |
| Blake                                                   |
| Clark                                                   |
| Scott                                                   |
| King                                                    |
| Turner                                                  |
| Adams                                                   |
| James                                                   |
| Ford                                                    |
| Miller                                                  |

## 14. Display the length of Your name using appropriate function. 
```sql
SELECT LENGTH('ANUSHKA');
```
# Output
| LENGTH('ANUSHKA') |
|-------------------|
|                7  |

## 15. Display the length of all the employee names. 
```sql
SELECT LENGTH(ename) FROM employee;
```
# Output
| LENGTH(ename) |
|---------------|
|            5  |
|            5  |
|            4  |
|            5  |
|            6  |
|            5  |
|            5  |
|            5  |
|            4  |
|            6  |
|            5  |
|            5  |
|            4  |
|            6  |
