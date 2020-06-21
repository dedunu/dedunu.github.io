---
layout: post
title: Common Table Expressions (CTE)
date: '2012-09-25T16:51:00.000+03:00'
author: Dedunu Dhananjaya
tags:
- SQL
- CTE
- T-SQL
- TSQL
- SQL Server
- Common Table Expressions
permalink: /2012/09/common-table-expressions-cte.html
---

```sql
USE AdventureWorks2012
GO

--Defining CTE
WITH Empl AS(SELECT * FROM HumanResources.Employee)
--Using CTE
SELECT Empl.* FROM Empl
GO
```

Moreover, you can use several `CTE`s in one statement.

```sql
USE AdventureWorks2012 
GO

--Defining CTE
WITH Empl AS ( SELECT * FROM HumanResources.Employee ),
Pers AS ( SELECT * FROM Person.Person )
--Using CTE
SELECT Empl.*, Pers.*
FROM Empl INNER JOIN Pers
ON Empl.BusinessEntityID = Pers.BusinessEntityID
GO
```