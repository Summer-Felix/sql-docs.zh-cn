---
title: "从跟踪提取脚本 (SQL Server Profiler) | Microsoft Docs"
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
  - "脚本 [SQL Server], 跟踪"
  - "从跟踪提取脚本 [SQL Server]"
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
caps.latest.revision: 20
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 20
---
# 从跟踪提取脚本 (SQL Server Profiler)
  本主题说明如何使用 [!INCLUDE[tsql](../../includes/tsql-md.md)] 从跟踪文件或表提取 [!INCLUDE[tsql](../../includes/tsql-md.md)] 事件并将它们保存为 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 脚本文件。  
  
### 从跟踪文件或表提取 Transact-SQL 脚本  
  
1.  打开一个包含要将其保存到 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本文件的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 事件的跟踪文件或表。 有关详细信息，请参阅[打开跟踪文件 (SQL Server Profiler)](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) 或[打开跟踪表 (SQL Server Profiler)](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)。  
  
2.  在“文件”菜单上，指向“导出”，再指向“提取 SQL Server 事件”，然后单击“提取 Transact-SQL 事件”。  
  
3.  在 **“另存为”** 对话框中，键入 [!INCLUDE[tsql](../../includes/tsql-md.md)] 文件的名称，然后单击 **“保存”**。  
  
## 另请参阅  
 [SQL Server 事件探查器](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  