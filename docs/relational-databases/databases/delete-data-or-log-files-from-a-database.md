---
title: "删除数据库中的数据文件或日志文件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "日志 [SQL Server], 文件"
  - "删除文件"
  - "删除文件"
  - "删除数据"
  - "数据删除 [SQL Server]"
  - "文件删除 [SQL Server]"
  - "删除数据"
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
caps.latest.revision: 33
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 33
---
# 删除数据库中的数据文件或日志文件
  本主题说明如何使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 在 [!INCLUDE[tsql](../../includes/tsql-md.md)]中删除数据文件或日志文件。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [先决条件](#Prerequisites)  
  
     [安全性](#Security)  
  
-   **删除数据库中的数据文件或日志文件，使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Prerequisites"></a> 先决条件  
  
-   文件必须为空后才能删除。 有关详细信息，请参阅[收缩文件](../../relational-databases/databases/shrink-a-file.md)。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 需要对数据库拥有 ALTER 权限。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### 删除数据库中的数据文件或日志文件  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 的实例，然后展开该实例。  
  
2.  展开“数据库”，右键单击要从其中删除文件的数据库，然后单击“属性”。  
  
3.  选择 **“文件”** 页。  
  
4.  在 **“数据库文件”** 网格中，选择要删除的文件，然后单击 **“删除”**。  
  
5.  单击“确定” 。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### 删除数据库中的数据文件或日志文件  
  
1.  连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。 此示例删除文件 `test1dat4`。  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../relational-databases/databases/codesnippet/tsql/delete-data-or-log-files_1.sql)]  
  
 有关更多示例，请参阅 [ALTER DATABASE 文件和文件组选项 (Transact-SQL)](../Topic/ALTER%20DATABASE%20File%20and%20Filegroup%20Options%20\(Transact-SQL\).md)。  
  
## 另请参阅  
 [收缩数据库](../../relational-databases/databases/shrink-a-database.md)   
 [向数据库中添加数据文件或日志文件](../../relational-databases/databases/add-data-or-log-files-to-a-database.md)  
  
  