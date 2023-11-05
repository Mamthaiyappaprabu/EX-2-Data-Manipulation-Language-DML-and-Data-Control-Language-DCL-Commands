# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## DATE :
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```

### OUTPUT:
![Screenshot 2023-10-07 171632](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/72dbae95-eaa2-4f3a-ba81-83bab39fc436)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
SQL> delete from manager where salary<2750;
```

### OUTPUT:
![Screenshot 2023-10-07 173611](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/a17d05e9-e1f9-4d2e-8bfe-8bcc88479ab2)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SQL> select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:

![Screenshot 2023-10-07 173624](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/285459b5-59d1-47c1-b3f3-53882d739831)


### Q4)	List the names of Clerks from emp table.


### QUERY:
```
SQL> select ename from manager where designation='clerk';
```

### OUTPUT:
![Screenshot 2023-10-07 173646](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/125589dc-a79b-4962-b8f6-7d17ada08d67)




### Q5)	List the names of employee who are not Managers.


### QUERY:
```
SQL> select ename from manager where designation <> 'manager';
```

### OUTPUT:
![Screenshot 2023-10-07 173658](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/d2e84135-d1f3-4373-9b51-248068aa1132)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
SQL> select ename from manager where commission=0;
```

### OUTPUT:
![Screenshot 2023-10-07 173711](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/b0fcb648-a06d-4130-a6f4-e82aad524008)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```
SQL> select ename from manager where ename like '%s' or ename like 's%';
```


### OUTPUT:
![Screenshot 2023-10-07 173730](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/58e2dede-8e57-4185-b655-9b0363c3a850)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
SQL> select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```


### OUTPUT:

![Screenshot 2023-10-07 173743](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/a30be936-04dc-4cc5-bbb4-6022a7fd6b03)

### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
SQL> select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:

![Screenshot 2023-10-07 173755](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/c0d08b71-babe-4250-b9f1-bcec48b5bb1e)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
SQL> select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![Screenshot 2023-10-07 173814](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/b53e5b5f-975f-4b41-91ea-b45cb730250e)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
SQL> select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![Screenshot 2023-10-07 173825](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/7ee30cdb-a76d-4809-a061-06eb1c7ca12d)

### Q12) Find number of rows in the table EMP

### QUERY:
```
SQL> select count(*) from manager;
```


### OUTPUT:

![Screenshot 2023-10-07 173830](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/bd02b21d-53df-4c1b-919a-b38f3c148a7b)


### Q13) Find maximum, minimum and average salary in EMP table.
### MAXIMUM :
### QUERY:
```
SQL> select max(salary) from manager;
```

### OUTPUT:
![Screenshot 2023-10-07 173835](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/6cc4f364-c510-4d5c-94c0-89d9ee85cd60)

### MINIMUM :
### QUERY:
```
SQL> select min(salary) from manager;
```
### OUTPUT :
![Screenshot 2023-10-07 173840](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/d79d30a2-e83f-4d74-9464-dc506c7530ca)

### AVERAGE :
### QUERY :
```
SQL> select avg(salary) from manager;
```
### OUTPUT :
![Screenshot 2023-10-07 173846](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/9fddce06-211c-45c8-be8f-6eb4a85ad5dd)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SQL> SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![Screenshot 2023-10-07 173909](https://github.com/Mamthaiyappaprabu/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393563/2f833199-4fdc-4695-b9f9-a9507378b1d8)

## RESULT :
Hence successfully created a manager database and execute DML queries using SQL.
