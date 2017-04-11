---
title: "修改视图 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-views"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "视图 [SQL Server], 重命名"
  - "视图 [SQL Server], 修改"
  - "修改视图"
  - "重命名视图"
ms.assetid: 2d3c14dc-43e5-4324-b8fb-f2692d330b16
caps.latest.revision: 22
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 22
---
# 修改视图
  视图定义之后，您可以使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 在 [!INCLUDE[tsql](../../includes/tsql-md.md)] 中修改其定义而无需删除并重新创建视图。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [限制和局限](#Restrictions)  
  
     [安全性](#Security)  
  
-   **修改视图，使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Restrictions"></a> 限制和局限  
  
-   修改视图并不会影响相关对象（例如，存储过程或触发器），除非对视图定义的更改使得该相关对象不再有效。  
  
-   如果当前所用的视图使用 ALTER VIEW 来修改，则 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 使用对该视图的排他架构锁。 在授予锁时，如果该视图没有活动用户，则 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 将从过程缓存中删除该视图的所有副本。 引用该视图的现有计划将继续保留在缓存中，但一旦被调用就会重新编译。  
  
-   ALTER VIEW 可应用于索引视图；但是，ALTER VIEW 会无条件地删除视图的所有索引。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 若要执行 ALTER VIEW，至少需要具有对 OBJECT 的 ALTER 权限。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### 修改视图  
  
1.  在 **“对象资源管理器”**中，单击视图所在的数据库旁边的加号，然后单击 **“视图”** 文件夹旁边的加号。  
  
2.  右键单击要修改的视图，然后选择“设计”。  
  
3.  在查询设计器的关系图窗格中，通过以下一种或多种方式更改视图：  
  
    1.  选中或清除要添加或删除的任何元素的复选框。  
  
    2.  在关系图窗格中右键单击，选择“添加表…”，然后从“添加表”对话框选择要添加到视图的其他列。  
  
    3.  右键单击要删除的表的标题栏，然后选择“删除”。  
  
4.  在“文件”菜单上，单击“保存”以保存*视图名称*。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### 修改视图  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的实例。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。 此示例首先创建一个视图，然后使用 ALTER VIEW 修改该视图。 将一个 WHERE 子句添加到该视图定义。  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    -- Create a view.  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
  
    -- Modify the view by adding a WHERE clause to limit the rows returned.  
    ALTER VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID  
    WHERE HireDate < CONVERT(DATETIME,'20020101',101) ;   
    GO  
    ```  
  
 有关详细信息，请参阅 [ALTER VIEW (Transact-SQL)](../../t-sql/statements/alter-view-transact-sql.md)。  
  
  