# SQL LAB - EXPERIMENT 0
## AIM:- 
To CREATE table (employee and department) and insert values in them.
## 1. CREATE DATABASE
```sql
CREATE DATABASE 2CSE22_31351;
```
## Output
| Message                    |
|----------------------------|
| Query OK, 1 row affected   |


# USing database
```sql
USE 2CSE22_31351;
```
# Output
| Message                              |
|--------------------------------------|
| Database changed                    |

## 2. CREATE TABLE (named employee)
```sql
CREATE TABLE employee (
    empno int (4) PRIMARY KEY,
    ename varchar (20) NOT NULL,
    job varchar (20),
    mgr int (4),
    hiredate date,
    sal int (10),
    comm int (7),
    deptno int (2)
);
```
# Output
| Message                        |
|---------------------------------|
| Query OK, 0 rows affected      |

# Describing table 
```sql
DESC employee;
```

# Output
| Field     | Type        | Null | Key | Default | Extra |
|-----------|------------|------|-----|---------|-------|
| empno     | int(4)     | NO   | PRI | NULL    |       |
| ename     | varchar(20)| NO   |     | NULL    |       |
| job       | varchar(20)| YES  |     | NULL    |       |
| mgr       | int(4)     | YES  |     | NULL    |       |
| hiredate  | date       | YES  |     | NULL    |       |
| sal       | int(10)    | YES  |     | NULL    |       |
| comm      | int(7)     | YES  |     | NULL    |       |
| deptno    | int(2)     | YES  |     | NULL    |       |

## 3. INSERTING VALUES IN employee table
```sql
INSERT INTO employee VALUES
(7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20),
(7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30),
(7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30),
(7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20),
(7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30),
(7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30),
(7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,20),
(7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40),
(7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20),
(7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30),
(7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20),
(7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30),
(7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20),
(7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);
```
# Output
| Message                         |
|----------------------------------|
| Query OK, 14 rows affected      |
| Records: 14  Duplicates: 0  Warnings: 0 |

## 4. SHOWING WHOLE TABLE 
```sql
SELECT * FROM employee;
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

## 5. CREATE TABLE (named department)
```sql
CREATE TABLE department (
    deptno int (2) PRIMARY KEY,
    dname varchar (15) NOT NULL
);
```
# Output
| Message                        |
|---------------------------------|
| Query OK, 0 rows affected      |

# Describing table
```sql
DESC department;
```
# Output
| Field   | Type         | Null | Key | Default | Extra |
|---------|-------------|------|-----|---------|-------|
| deptno  | int(2)      | NO   | PRI | NULL    |       |
| dname   | varchar(15) | NO   |     | NULL    |       |

## 6. INSERTING VALUES IN deoartment table
```sql
INSERT INTO department VALUES
(10, 'RESEARCH'),
(20, 'ACCOUNTING'),
(30, 'SALES'),
(40, 'OPERATIONS');
```
# Output
| Message                         |
|----------------------------------|
| Query OK, 4 rows affected       |
| Records: 4  Duplicates: 0  Warnings: 0 |

## 7. SHOWING WHOLE TABLE
```sql
SELECT * FROM department;
```
# Output
| deptno | dname       |
|--------|------------|
| 10     | RESEARCH   |
| 20     | ACCOUNTING |
| 30     | SALES      |
| 40     | OPERATIONS |
