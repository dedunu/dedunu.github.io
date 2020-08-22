---
layout: post
title: How to take list of databases in SQL Server
date: '2012-11-12T18:03:00.000+02:00'
author: Dedunu Dhananjaya
tags:
- SQL
- SQLPS
- Powershell
- Administration
- SQLCMD
- SQL Server
- SQL Sever
permalink: /2012/11/how-to-take-list-of-databases-in-sql.html
---

In SQLCMD and Powershell I wanted to take the list of databases. In MySQL “show databases” command was there. But in `SQLCMD` I was unable to find such a command.  

```sql
--Stored Procedure
EXEC sp_databases  
GO   
  
--SELECT Statement
SELECT Name FROM master.dbo.sysdatabases  
GO 
```
  
You can use the above commands in SSMS (if you are lazy to move your mouse to object explorer) and SQLCMD. Also, you can use the same thing on PowerShell too.  

```powershell
# Stored Procedure
Invoke-SQLCMD "EXEC sp\_databases"  

# SELECT Statement
Invoke-SQLCMD "SELECT Name FROM master.dbo.sysdatabases"
```

But in SQLPS you can go to your SQL Server instance’s database and just type “dir”.
