# Computer Science II
## Lab 7.0 - MySQL

An introduction to Structured Query Language (SQL) used in databases.

This is a lab used in Computer Science II (CSCE 156) for Fall 2023 
in the [School of Computing](https://computing.unl.edu) 
at the [University of Nebraska-Lincoln](https://unl.edu).

## Overview

### Resources

-   Information about databases and tables  
        <http://dev.mysql.com/doc/refman/5.6/en/getting-information.html>

-   Creating table  
        <https://www.w3schools.com/sql/sql_create_db.asp>

-   Inserting data  
        <http://www.w3schools.com/sql/sql_insert.asp>

-   Retrieving data  
        <http://www.w3schools.com/sql/sql_select.asp>

-   Conditional clause  
        <http://www.w3schools.com/sql/sql_where.asp>


    
### Lab Objectives & Topics

Following the lab, you should be able to:

-   connect to a database

-   perform some basic database operations

Note that the lab may involve some concepts or statements not covered (yet) in the class. You should be able to complete the lab without fully understanding them. If you have any questions about them, please feel free to ask our LAs. 


### Peer Programming Pair-Up

At the start of
each lab, you may find a team member by yourself or may be randomly paired up with another student by
a lab instructor.  One of you will be designated the *driver* 
and the other the *navigator*. If you prefer to work on this lab by yourself, that is fine too.  Each week you should try to alternate: if you were a driver 
last week, be a navigator next, etc. 

***Note that, each student must answer the lab questions on Canvas for grading.***

## 1. Install MySQL Workbench

MySQL is a free Integrated Development Environment (IDE) for MySQL.  You can download and install
MySQL Workbench at the following URL.

https://www.mysql.com/products/workbench/
    

## 2. Connect to MySQL server on Linux server

We will use the MySQL server running on a Linux server of School of Computing.

1. Create a new MySQL connection by clicking the plus sign 
<p align="center">
<img src="images/Workbench-1.png" alt="create a new connection" width="70%"/>
</p>  

2. Type the hostname `cse-linux-01.unl.edu`, your MySQL username (e.g., my MySQL username is lxu3), and a connection name (e.g., UNLCSE). We will use the default port number 3306. 
<p align="center">
<img src="images/Workbench-2.png" alt="hostname" width="70%"/>
</p>  

3. Open the MySQL connection 
<p align="center">
<img src="images/Workbench-3.png" alt="open a new connection" width="70%"/>
</p>  

4. Type your MySQL password, and select "Continue Anyway" if there is a "Connection Warning". Then you will be connected to the MySQL server. 
<p align="center">
<img src="images/Workbench-4.png" alt="connect" width="70%"/>
</p>  

## 3. Activities 

Type and execute the following MySQL statements.

Note that after typing each statement, please click the icon highlighted in the red box to execute the statement. Also note that if MySQL Workbench does not find any error in a statement, there is a blue dot before the statement.
<p align="center">
<img src="images/Workbench-5.png" alt="execute" width="50%"/>
</p>  

If MySQL Workbench finds an error in a statement, there is a red x before the statement. For example, line 3 in the following screenshot has a typo `iff`.
<p align="center">
<img src="images/Workbench-6.png" alt="invalid" width="50%"/>
</p>  

### 3.1 Select your database

Replace `lxu3` in the following statement with your MySQL username. 

```sql
use lxu3;
```

### 3.2 Create a new table

```sql
drop table if exists Student;
create table Student (
	studentID int not null,
	studentName varchar(255) not null,
	studentYear int,
	studentMajor char(2) not null default "CS",
        primary key (studentID)
);
```


### 3.3 Insert data to the table

```sql
insert into Student (studentID, studentName, studentYear, studentMajor) 
  values (1, "Alice", 2010, "CS"),
         (2, "Bob", 2011, "CE"),
         (3, "Crystal", 2012, "SE");
insert into Student 
  values (4, "David", 2013, "CE");
insert into Student (studentID, studentName) 
  values (5, "Emma");
```

### 3.4 Query the table

Try the following queries.

```sql
select * from Student;
select studentName from Student;
select studentName from Student where studentMajor="CS" and studentYear<=2012;
select * from Student where studentYear<=2012 order by studentName;
```

## 4. Answer the lab questions on Canvas

* You do not need to submit any code for this lab. Instead please answer the lab questions on Canvas. 
