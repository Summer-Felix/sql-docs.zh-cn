---
title: "数据迁移设置 (MySQLToSQL) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssma-mysql
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 9c396df4-5676-4f32-9c57-70d4f15f9b7a
caps.latest.revision: "9"
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5776d0e27ab6d68b83ce0e8ce7c9ddb667b13f1a
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="data-migration-settings-mysqltosql"></a>数据迁移设置 (MySQLToSQL)
  
## <a name="data-migration-settings"></a>数据迁移设置  
**数据迁移设置**允许用户编写自定义查询对于数据迁移。  
  
-   时，此选项卡才可用**扩展数据迁移选项**设置为**显示**并且当设置为时隐藏**隐藏**项目设置。 有关项目迁移设置的详细信息，请参阅[项目设置 （迁移）](http://msdn.microsoft.com/en-us/2a3cba9e-cd54-4a8b-b858-8fc4cf2580d9) 。  
  
-   将在中实现的自定义 SQL 语句的分析**数据迁移设置**表节点的选项卡。  
  
-   以下是两个中提供的复选框**数据迁移设置**viz。:  
  
    1.  截断的 SQL Server 表  
  
    2.  使用自定义选择  
  
1.  **截断的 SQL Server 表：**  
     此选项允许用户在目标数据库已迁移的数据的清除视图。  
  
    -   默认情况下，会检查此文本框。  
  
    -   如果未选中此文本框中，则迁移的数据将添加到在目标数据库的现有数据。  
  
2.  **使用自定义选择：**  
     此选项允许用户修改**选择**语句存在 (**选择**语句允许用户选择要显示在目标数据库的数据)。  
  
    1.  默认情况下，此文本框为未选中状态。  
  
    2.  如果选中此文本框中，则它允许用户修改**选择**存在的语句。  
  
有两个按钮存在 viz。:  
  
-   **应用：**单击**应用**将已更改的设置。  
  
-   **取消:**单击**取消**之前进行的更改已还原存在的设置。  
  
## <a name="see-also"></a>另请参阅  
[将 MySQL 数据迁移到 SQL Server/SQL Azure](http://msdn.microsoft.com/en-us/a6a7f4d6-68aa-4a38-93bf-53eba0d7dc82)  
  
