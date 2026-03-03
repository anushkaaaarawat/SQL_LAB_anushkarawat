# SQL LAB - EXPERIMENT 2
## AIM:- 
To retrieve information from the Employee table using SQL  SELECT queries with different conditions and operators.
## 1. List all distinct job in Employee.
```sql
SELECT DISTINCT job 
FROM employee;
```
# Output
| job       |
|-----------|
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |

## 2. List all information about employee in Department Number 30.
```sql
SELECT * 
FROM employee 
WHERE deptno = 30;
```
# Output
| empno | ename  | job      | mgr  | hiredate   | sal  | comm | deptno |
|-------|--------|----------|------|------------|------|------|--------|
| 7499  | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250 | 300  | 30     |
| 7654  | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7844  | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 | 0    | 30     |
| 7900  | JAMES  | CLERK    | 7698 | 1981-12-03 | 950  | NULL | 30     |

## 3. Find all department number with department names greater than 20.
```sql
SELECT deptno, dname 
FROM department 
WHERE deptno > 20;
```
# Output
| deptno | dname       |
|--------|------------|
| 30     | SALES      |
| 40     | OPERATIONS |

## 4. Find all information about all the managers as well as the clerks in department 30.
```sql
SELECT * 
FROM employee 
WHERE deptno = 30 
AND (job = 'MANAGER' OR job = 'CLERK');
```
# Output
| empno | ename | job     | mgr  | hiredate   | sal  | comm | deptno |
|-------|-------|---------|------|------------|------|------|--------|
| 7698  | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7900  | JAMES | CLERK   | 7698 | 1981-12-03 | 950  | NULL | 30     |

## 5. List the Employee name, Employee numbers and department of all clerks.
```sql
SELECT ename, empno, deptno 
FROM employee 
WHERE job = 'CLERK';
```
# Output
| ename  | empno | deptno |
|--------|-------|--------|
| SMITH  | 7369  | 20     |
| ADAMS  | 7876  | 20     |
| JAMES  | 7900  | 30     |
| MILLER | 7934  | 10     |

## 6. Find all managers not in department 30.
```sql
SELECT * 
FROM employee 
WHERE job = 'MANAGER' 
AND deptno <> 30;
```
# Output
| empno | ename | job     | mgr  | hiredate   | sal  | comm | deptno |
|-------|-------|---------|------|------------|------|------|--------|
| 7566  | JONES | MANAGER | 7839 | 1981-04-02 | 2975 | NULL | 20     |
| 7782  | CLARK | MANAGER | 7839 | 1981-06-09 | 2450 | NULL | 20     |

## 7. List information about all Employees in department 10 who are not manager or clerks.
```sql
SELECT * 
FROM employee 
WHERE deptno = 10 
AND job NOT IN ('MANAGER', 'CLERK');
```
# Output
| Message                         |
|---------------------------------|
| Empty Set                       |

## 8. Find Employees and jobs earning between 1200 and 1400.
```sql
SELECT ename, job 
FROM employee 
WHERE sal BETWEEN 1200 AND 1400;
```
# Output
| ename  | job      |
|--------|----------|
| WARD   | SALESMAN |
| MARTIN | SALESMAN |
| MILLER | CLERK    |

## 9. List Name and Department Number of employee who are clerks, analyst or salesman.
```sql
SELECT ename, deptno 
FROM employee 
WHERE job IN ('CLERK', 'ANALYST', 'SALESMAN');
```
# Output
| ename  | deptno |
|--------|--------|
| SMITH  | 20     |
| ALLEN  | 30     |
| WARD   | 30     |
| MARTIN | 30     |
| SCOTT  | 40     |
| TURNER | 30     |
| ADAMS  | 20     |
| JAMES  | 30     |
| FORD   | 20     |
| MILLER | 10     |

## 10. List Name and Department Number of employee whose names begin with M.
```sql
SELECT ename, deptno 
FROM employee 
WHERE ename LIKE 'M%';
```
# Output
| ENAME  | DEPTNO |
|--------|--------|
| MARTIN | 30     |
| MILLER | 10     |
