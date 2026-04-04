# SQL LAB - EXPERIMENT 4
## AIM:- 
To perform various SQL queries on the **EMPLOYEE** table to retrieve, filter, and manipulate data using different SQL clauses such as WHERE, LIKE, IN, BETWEEN, ORDER BY, and aggregate calculations.
## 1. Display the list of employees who have joined the company before 30th June 80 or after 31st Dec 81. 
```sql
SELECT * 
FROM employee 
WHERE hiredate < '1980-06-30' 
OR hiredate > '1981-12-31';
```
# Output
| empno | ename  | job     | mgr  | hiredate   | sal  | comm | deptno |
|-------|--------|---------|------|------------|------|------|--------|
| 7788  | SCOTT  | ANALYST | 7566 | 1982-12-09 | 3000 | NULL | 40     |
| 7876  | ADAMS  | CLERK   | 7788 | 1983-01-12 | 1100 | NULL | 20     |
| 7934  | MILLER | CLERK   | 7782 | 1982-01-23 | 1300 | NULL | 10     |

## 2. Display the names of employees whose names have second alphabet A in their names. 
```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_A%';
```
# Output
| ename  |
|--------|
| WARD   |
| MARTIN |
| JAMES  |

## 3. Display the names of employees whose name is exactly five characters in length.
```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_____';
```
# Output
| ename |
|-------|
| SMITH |
| ALLEN |
| JONES |
| BLAKE |
| CLARK |
| SCOTT |
| ADAMS |
| JAMES |

## 4. Display the names of employees whose names have second alphabet A in their names.
```sql
SELECT ename 
FROM employee 
WHERE ename LIKE '_A%';
```
# Output
| ename  |
|--------|
| JAMES  |
| WARD   |
| MARTIN |

## 5. Display the names of employees who are not working as salesman or clerk or analyst. 
```sql
SELECT ename 
FROM employee 
WHERE job NOT IN ('CLERK','SALESMAN','ANALYST');
```
# Output
| ename |
|-------|
| JONES |
| BLAKE |
| CLARK |
| KING  |

## 6. Display the name of the employee along with their annual salary (sal*12). The name of the employee earning highest salary should appear first. 
```sql
SELECT ename, (sal * 12) AS annual_sal 
FROM employee 
ORDER BY annual_sal DESC;
```
# Output
| ename  | annual_salary |
|--------|---------------|
| KING   | 60000         |
| SCOTT  | 36000         |
| FORD   | 36000         |
| JONES  | 35700         |
| BLAKE  | 34200         |
| CLARK  | 29400         |
| ALLEN  | 19200         |
| TURNER | 18000         |
| MILLER | 15600         |
| MARTIN | 15000         |
| WARD   | 15000         |
| ADAMS  | 13200         |
| JAMES  | 11400         |
| SMITH  | 9600          |

## 7. Display name, sal, hra, pf, da, totalsal for each employee. The output should be in the order of total sal, hra 15% of sal, da 10% of sal, pf 5% of sal. Total salary will be (sal*hra*da)-pf. 
```sql
SELECT ename, 
       (sal*(0.15 * sal) * (0.1 * sal)) - (0.5 * sal) AS total_sal, (0.15 * sal) AS hra, (0.1 * sal) AS da
        (0.5 * sal) AS pf FROM employee;
```
# Output
| ename  | total_sal       | hra    | da    | pf     |
|--------|-----------------|--------|-------|--------|
| SMITH  | 7679600.000     | 120.00 | 80.0  | 400.0  |
| ALLEN  | 61439200.000    | 240.00 | 160.0 | 800.0  |
| WARD   | 29296250.000    | 187.50 | 125.0 | 625.0  |
| JONES  | 394957653.125   | 446.25 | 297.5 | 1487.0 |
| MARTIN | 29296250.000    | 187.50 | 125.0 | 625.0  |
| BLAKE  | 3472235450.000  | 427.50 | 285.0 | 1425.0 |
| CLARK  | 220590650.000   | 367.50 | 254.0 | 1225.0 |
| SCOTT  | 484998500.000   | 450.00 | 300.0 | 1500.0 |
| KING   | 1874997500.000  | 750.00 | 500.0 | 2500.0 |
| TURNER | 50624250.000    | 225.00 | 150.0 | 750.0  |
| ADAMS  | 19964450.000    | 165.00 | 110.0 | 550.0  |
| JAMES  | 12860150.000    | 142.00 | 95.0  | 475.0  |
| FORD   | 404998500.000   | 450.00 | 300.0 | 1500.0 |
| MILLER | 32954350.000    | 195.00 | 130.0 | 650.0  |

## 8. Update the salary of each employee by 10% increment who are not eligible for commission. 
```sql
UPDATE employee 
SET sal = 1.1 * sal WHERE comm IS NULL;
```
# Output
Query OK, 10 rows affected

## 9. Display those employees whose salary is more than 3000 after giving 20% increment. 
```sql
SELECT * 
FROM employee 
WHERE (sal * 1.2) > 3000;
```
# Output
| empno | ename | job       | mgr  | hiredate   | sal  | comm | deptno |
|-------|-------|-----------|------|------------|------|------|--------|
| 7566  | JONES | MANAGER   | 7839 | 1981-04-02 | 3273 | NULL | 20     |
| 7698  | BLAKE | MANAGER   | 7839 | 1981-05-01 | 3135 | NULL | 30     |
| 7782  | CLARK | MANAGER   | 7839 | 1981-06-09 | 2695 | NULL | 20     |
| 7839  | KING  | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL | 20     |
| 7902  | FORD  | ANALYST   | 7566 | 1981-12-03 | 3300 | NULL | 20     |

## 10. Display those employees whose salary contains atleast 3 digits. 
```sql
SELECT * 
FROM employee 
WHERE sal >= 100;
```
# Output
| empno | ename  | job       | mgr  | hiredate   | sal  | comm | deptno |
|-------|--------|-----------|------|------------|------|------|--------|
| 7369  | SMITH  | CLERK     | 7902 | 1980-12-17 | 800  | NULL | 20     |
| 7499  | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 | 300  | 30     |
| 7566  | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL | 20     |
| 7654  | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7782  | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL | 20     |
| 7788  | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL | 40     |
| 7839  | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL | 20     |
| 7844  | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 | 0    | 30     |
| 7876  | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL | 20     |
| 7900  | JAMES  | CLERK     | 7698 | 1981-12-03 | 950  | NULL | 30     |
| 7902  | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL | 20     |
| 7934  | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL | 10     |
