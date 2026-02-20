# SQL Lab Experiment-3
## Aim
1. List all employees and jobs in Department 30 in descending
order by salary.
2. List job and Department Number of employees whose name
are five letters long begin with “A” and end with “N”.
3. Display the name of employees whose name start with
alphabet S.
4. Display the names of employees whose name ends with
alphabet S.
5. Display the names of employees working in department
number 10 or 20 or 40 or employees working as clerks,
salesman or analyst.
6. Display employee number and names for employees who earn
commission.
7. Display employee number and total salary for each employee.
8. Display employee number and annual salary for each
employee.
9. Display the names of all employees working as clerks and
drawing a salary more than 3,000.
10. Display the names of employees who are working as clerk,
salesman or analyst and drawing a salary more than 3,000.
## Query
## 1. Employees & jobs in Dept 30, ordered by salary (DESC)

 ORDER BY sal DESC → highest salary first

```sql
SELECT ename, job, sal FROM employee
WHERE deptno = 30 ORDER BY sal DESC;
```

## 2. Job & DeptNo of employees

Name = 5 letters, starts with A and ends with N

\_ → exactly one character

```sql
SELECT job, deptno FROM employee
WHERE ename LIKE 'A___N';
```

## 3. Names of employees starting with S

```sql
SELECT ename FROM employee
WHERE ename LIKE 'S%';
```

## 4. Names of employees ending with S

```sql
SELECT ename FROM employee
WHERE ename LIKE '%S';
```

## 5. Employees working in Dept 10 / 20 / 40

OR working as Clerk / Salesman / Analyst

```sql
SELECT ename FROM employee
WHERE deptno IN (10,20,40) OR job IN ('CLERK','SALESMAN','ANALYST');

```

## 6. Employee number & name of employees who earn commission

```sql
SELECT empno, ename FROM employee
WHERE comm IS NOT NULL AND comm > 0; --IS NOT NULL → commission exists
```

## 7. Employee number & total salary for each employee

(Salary + Commission)

```sql
SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM employee; -- IFNULL(comm,0) avoids NULL issue
```

## 8. Employee number & annual salary

```sql
SELECT empno, sal*12 AS annual_salary FROM employee;
```

## 9. Employees who are clerks earning > 3000

```sql
SELECT ename FROM employee
WHERE job = 'CLERK' AND sal > 3000;
```

## 10. Employees who are clerk / salesman / analyst and earning > 3000

```sql
SELECT ename FROM employee
WHERE job IN ('CLERK','SALESMAN','ANALYST') AND sal > 3000;
```