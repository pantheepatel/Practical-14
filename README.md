# Practical 14: Entity Framework Database First

This document provides setup instructions for Practical 14, focusing on database configuration using Entity Framework Database First approach.

## Database Setup

### Create Database
```sql
CREATE DATABASE Practical14
USE Practical14
```

### Create Employee Table
```sql
CREATE TABLE Employee (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    DOB DATE NOT NULL,
    Age INT
);
```

### Sample Data (Optional)
Run the following query to insert sample data for pagination and search functionality testing:

```sql
INSERT INTO Employee (Name, DOB, Age) VALUES
('Alice', '1990-05-01', 34),
('Bob', '1985-07-15', 39),
('Charlie', '1992-03-12', 33),
('David', '1988-11-21', 36),
('Eve', '1995-09-10', 29),
('Frank', '1991-01-05', 33),
('Grace', '1993-06-25', 31),
('Hank', '1987-08-17', 37),
('Ivy', '1996-10-30', 28),
('Jack', '1990-12-14', 34),
('Kathy', '1989-04-09', 35),
('Leo', '1986-02-23', 38),
('Mona', '1994-07-11', 30),
('Nate', '1993-11-19', 31),
('Olivia', '1995-03-08', 29),
('Paul', '1992-05-20', 32),
('Quincy', '1988-06-02', 36),
('Rachel', '1997-08-29', 27),
('Sam', '1991-09-15', 33),
('Tina', '1989-12-25', 35),
('Uma', '1990-10-05', 34),
('Victor', '1987-01-18', 37),
('Wendy', '1994-02-14', 30),
('Xander', '1996-04-07', 28),
('Yara', '1993-08-03', 31);
```

## Connection String Configuration

Update the `web.config` file with the following connection string:

```xml
<connectionStrings>
  <add name="EmployeeEntities" 
       connectionString="metadata=res://*/Models.EmployeeModel.csdl|res://*/Models.EmployeeModel.ssdl|res://*/Models.EmployeeModel.msl;provider=System.Data.SqlClient;provider connection string=&quot;data source=.\SQLEXPRESS;initial catalog=Practical14;integrated security=True;trustservercertificate=True;MultipleActiveResultSets=True;App=EntityFramework&quot;" 
       providerName="System.Data.EntityClient" />
</connectionStrings>
```

> **Note:** Modify the connection string if your SQL Server instance differs from `.\SQLEXPRESS`.

## Troubleshooting

If you encounter issues:
- Verify SQL Server is running
- Ensure the connection string points to the correct SQL Server instance
