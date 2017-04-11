---
title: "更改数据库兼容性模式和使用 Query Store | Microsoft Docs"
ms.custom: ""
ms.date: "09/22/2015"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "setup-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "查询计划 [SQL Server]，迁移"
  - "升级 SQL Server，迁移查询计划"
  - "计划指南 [SQL Server]，迁移查询计划"
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
caps.latest.revision: 19
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 17
---
# 更改数据库兼容性模式和使用 Query Store
  在 SQL Server 2016 中，一些更改仅在数据库的 DATABASE_COMPATIBILITY 级别更改为 130 后才会启用。  执行此操作的原因如下：  
  
-   由于升级是单向操作（不可能降级文件格式），将新功能的启用分离为数据库内的单独操作有一定作用。  可以将一个设置恢复到之前的 DATABASE_COMPATIBILITY 级别。  新的模式可以减少中断期间必然发生的事件的数量。  
  
-   更改查询处理器可能会产生复杂的影响。  即使对系统进行的是“较好的”更改（对大多数客户而言可能是非常好的更改），也可能在其他地方导致重要查询的不可接受的回归。  从升级过程中分离此逻辑允许 Query Store 等功能在生产服务器中快速缓解计划选择回归或甚至完全将其规避。  
  
> [!NOTE]  
>  如果升级前用户数据库的兼容级别为 100 或更高，升级后将保持相应级别。 如果升级前兼容级别为 90，则在升级后的数据库中，兼容级别将设置为 100，该级别为 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 支持的最低兼容级别。  
  
 用于启用新查询处理器功能的升级过程与产品的发布后服务模式相关。  这些修补程序中的一些发布在跟踪标志 4199 下。  需要修补程序的客户可以选择加入这些修补程序而不会导致其他客户的意外回归。  查询处理器修补程序的发布后服务模式记录于[此处](https://support.microsoft.com/en-us/kb/974006)。 从 SQL Server 2016 开始，转换到新的兼容级别意味着不再需要 4199 跟踪标志，因为在最新的兼容模式 (130) 中这些修复程序现在为默认启用。  因此，作为升级过程的一部分，验证升级过程完成后未启用 4199 是很重要的。  
  
 用于将查询处理器升级到最新版本的代码的建议工作流如下：  
  
1.  将数据库升级到 SQL Server 2016，而无需更改数据库兼容级别（保持为之前的级别）  
  
2.  在数据库上启用查询存储。 有关启用和使用查询存储的详细信息，请参阅 [Monitoring Performance By Using the Query Store](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)。  
  
3.  请等待足够长的时间以收集工作负荷的代表性数据。  
  
4.  将数据库的兼容级别更改为 130。  
  
5.  使用 SQL Server Management Studio 评估兼容级别更改后特定查询上是否存在性能回归  
  
6.  对于出现回归的情况，则在查询存储中强制执行之前的计划。  
  
7.  如果存在未能强制执行的查询计划，或者如果性能仍不足，请考虑将兼容级别还原到之前的设置，然后寻求 Microsoft 客户支持。  
  
## 另请参阅  
 [查看或更改数据库的兼容级别](../../relational-databases/databases/view-or-change-the-compatibility-level-of-a-database.md)  
  
  