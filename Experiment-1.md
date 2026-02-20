# SQL Lab-Experiment 1
## Aim
1. Create Employee_master table with data using Employee
table.
2. Delete all record into Employee_master whose DeptNo is 10
3. Update 10% in his salary of DEPTNO 20 into
Employee_Master.
4. Alter SAL with size 10,2 in Employee_Master.
5. Drop Employee_master Table.
## Query
### 1. Create employee_master table with data using employee table.
```sql 
CREATE TABLE employee_master AS
SELECT * FROM employee;
```
### 2.Delete all records from Employee_master whose DeptNo is 10
```sql
DELETE FROM employee_master
WHERE deptno = 10;
```
### 3.Update salary by 10% for DeptNo 20
```sql 
UPDATE employee_master
SET sal = sal + (sal * 0.10)
WHERE deptno = 20;
```
### 4.Alter SAL with size 10,2 in Employee_master
```sql
ALTER TABLE employee_master
MODIFY sal DECIMAL(10,2);
```
### 5.Drop Employee_master table
```sql 
DROP TABLE employee_master;
```
### 
 

