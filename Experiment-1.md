# SQL LAB - EXPERIMENT 1
## AIM:- 
To Perform data manipulation and definition operations on the employee table using SQL commands like CREATE, DELETE, UPDATE, ALTER and DROP.
## 1. Create Employee_master table with data using Employee 
```sql
CREATE TABLE employee_master AS 
SELECT * FROM employee;
```
# Output
| Message                        |
|---------------------------------|
| Query OK, 14 rows affected     |
| Records: 14  Duplicates: 0  Warnings: 0 |

# Verification Query
```sql
SELECT * FROM employee_master;
```
# Verification Output
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

## 2. Delete all record into Employee_master whose DeptNo is 10 
```sql
DELETE FROM employee_master 
WHERE deptno = 10;
```
# Output
| Message                       |
|--------------------------------|
| Query OK, 1 row affected      |

# Verification Query
```sql
SELECT * FROM employee_master;
```
# Verification Output (After Deletion)
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

## 3. Update 10% in his salary of DEPTNO 20 into Employee_Master.
```sql
UPDATE employee_master 
SET sal = sal + (sal * 0.10)
WHERE deptno = 20;
```
# Output
| Message                       |
|--------------------------------|
| Query OK, 6 rows affected     |
| Rows matched: 6  Changed: 6  Warnings: 0 |

# Verification Query
```sql
SELECT * FROM employee_master 
WHERE deptno = 20;
```
# Verification Output
| empno | ename  | job       | mgr  | hiredate   | sal  | comm | deptno |
|-------|--------|-----------|------|------------|------|------|--------|
| 7369  | SMITH  | CLERK     | 7902 | 1980-12-17 | 880  | NULL | 20     |
| 7566  | JONES  | MANAGER   | 7839 | 1981-04-02 | 3272 | NULL | 20     |
| 7782  | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695 | NULL | 20     |
| 7839  | KING   | PRESIDENT | NULL | 1981-11-17 | 5500 | NULL | 20     |
| 7876  | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210 | NULL | 20     |
| 7902  | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300 | NULL | 20     |

## 4. Alter SAL with size 10,2 in Employee_Master.
```sql
ALTER TABLE employee_master 
MODIFY sal DECIMAL(10,2);
```
# Output
| Message                        |
|---------------------------------|
| Query OK, 13 rows affected      |
| Records: 13  Duplicates: 0  Warnings: 0 |

# Verification Query
```sql
SELECT * FROM employee_master;
```
# Verification Output
| empno | ename  | job       | mgr  | hiredate   | sal      | comm | deptno |
|-------|--------|-----------|------|------------|----------|------|--------|
| 7369  | SMITH  | CLERK     | 7902 | 1980-12-17 | 880.00   | NULL | 20     |
| 7499  | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600.00  | 300  | 30     |
| 7521  | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250.00  | 300  | 30     |
| 7566  | JONES  | MANAGER   | 7839 | 1981-04-02 | 3272.50  | NULL | 20     |
| 7654  | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250.00  | 1400 | 30     |
| 7698  | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850.00  | NULL | 30     |
| 7782  | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695.00  | NULL | 20     |
| 7788  | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000.00  | NULL | 40     |
| 7839  | KING   | PRESIDENT | NULL | 1981-11-17 | 5500.00  | NULL | 20     |
| 7844  | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500.00  | 0    | 30     |
| 7876  | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210.00  | NULL | 20     |
| 7900  | JAMES  | CLERK     | 7698 | 1981-12-03 | 950.00   | NULL | 30     |
| 7902  | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300.00  | NULL | 20     |

## 5. Drop Employee_master Table.
```sql
DROP TABLE employee_master;
```
# Output
| Message                        |
|--------------------------------|
| Query OK, 0 rows affected      |

# Verification Query
```sql
SHOW TABLES;
```
# Verification Output
| Tables_in_2CSE22_31351   |
|--------------------------|
| department               |
| employee                 |
