# Employee Management System
An employee management system with CRUD functionality. It uses ADO .NET to connect to SQL server database and Stored Procedures to execute database operations.
## Prerequisites
1. .NET 6.0.406
2. SQL Server
3. Nuget Package: System.Data.SqlClient 4.8.5 Version

# SQL Query and Stored Procedures used in Database
### 1. To create Employee table using SQL
```
Create table tblEmployee(    
    EmployeeId int IDENTITY(1,1) NOT NULL,    
    Name varchar(20) NULL,    
    City varchar(20) NULL,    
    Department varchar(20) NULL,    
    Gender varchar(6) NULL    
)  
```
## 1. To add Employee record
```
Create procedure spAddEmployee     
(    
    @Name VARCHAR(20),     
    @City VARCHAR(20),    
    @Department VARCHAR(20),    
    @Gender VARCHAR(6)    
)    
as     
Begin     
    Insert into tblEmployee (Name,City,Department, Gender)     
    Values (@Name,@City,@Department, @Gender)     
End 
```
## 2. To update Employee record
```
Create procedure spUpdateEmployee      
(      
   @EmpId INTEGER ,    
   @Name VARCHAR(20),     
   @City VARCHAR(20),    
   @Department VARCHAR(20),    
   @Gender VARCHAR(6)    
)      
as      
begin      
   Update tblEmployee       
   set Name=@Name,      
   City=@City,      
   Department=@Department,    
   Gender=@Gender      
   where EmployeeId=@EmpId      
End  
```
## 3. To delete Employee record
```
Create procedure spDeleteEmployee     
(      
   @EmpId int      
)      
as       
begin      
   Delete from tblEmployee where EmployeeId=@EmpId      
End   
```
## 4. To view all Employee record
```
Create procedure spGetAllEmployees    
as    
Begin    
    select *    
    from tblEmployee    
End  
```
## Screenshots
- Create Employee
![Create](/screenshots/Create.PNG)
- After creating Employee
 ![AfterCreate](/screenshots/AfterCreate.PNG)
- Details of an Employee
![Detail](/screenshots/Details.PNG)
- Edit Employee
![Edit](/screenshots/Edit1.PNG)
- After editing an Employee
![Edit2](/screenshots/Edit2.PNG)
- Delete Employee
![Delete](/screenshots/Delete1.PNG)
- After deleting Employee
![AfterDelete](/screenshots/Delete2.PNG)