---
title: "收缩数据库任务 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.shrinkdatabasetask.f1"
helpviewer_keywords: 
  - "收缩数据库任务"
  - "数据库收缩 [Integration Services]"
  - "收缩数据库"
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
caps.latest.revision: 42
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 42
---
# 收缩数据库任务
  收缩数据库任务可以减少 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据库数据和日志文件的大小。  
  
 使用收缩数据库任务，包可以为单个或多个数据库收缩文件。  
  
 收缩数据文件通过将数据页从文件末尾移动到更靠近文件开头的未占用的空间来恢复空间。 在文件末尾创建足够的可用空间后，可以取消对文件末尾的数据页的分配并将它们返回给文件系统。  
  
> [!WARNING]  
>  被移动用来收缩文件的数据可以分布到文件的任何可用位置。 这将导致索引碎片并使搜索索引范围的查询变慢。 若要消除碎片，请考虑在收缩后重新生成文件的索引。  
  
## 命令  
 收缩数据库任务封装了 DBCC SHRINKDATABASE 命令，其中包括下列参数和选项：  
  
-   *database_name*  
  
-   *target_percent*  
  
-   NOTRUNCATE 或 TRUNCATEONLY。  
  
 如果收缩数据库任务收缩多个数据库，则该任务将对每个数据库都运行一次 SHRINKDATABASE 命令。 除了 *database_name* 参数以外，SHRINKDATABASE 命令的所有实例均使用相同的参数值。 有关详细信息，请参阅 [DBCC SHRINKDATABASE (Transact-SQL)](../../t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql.md)。  
  
## 配置收缩数据库任务  
 可以通过 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器设置属性。 此任务位于 **设计器中** “工具箱” **的** “维护计划中的任务” [!INCLUDE[ssIS](../../includes/ssis-md.md)] 部分。  
  
 有关可在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置的属性的详细信息，请单击下面的主题：  
  
-   [“收缩数据库”任务（维护计划）](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 有关在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中设置这些属性的详细信息，请单击以下主题：  
  
-   [设置任务或容器的属性](../Topic/Set%20the%20Properties%20of%20a%20Task%20or%20Container.md)  
  
  