---
title: "SQL Server 数据库引擎和 Azure SQL 数据库的性能中心 | Microsoft Docs"
ms.custom: 
ms.date: 04/08/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.reviewer: 
ms.service: 
ms.component: performance
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Performance (SQL Server)
- Performance (SQL Database)
helpviewer_keywords:
- SQL Server, performance
- performance (SQL Server)
- database performance (SQL Server)
- SQL Database (Performance)
- performance (SQL Database)
- database performance (SQL Database)
ms.assetid: 301204b2-140d-4495-98ed-021a9b5025f5
caps.latest.revision: 
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: f17dd20a0a6c3ffd93cc89dd97140341ed893383
ms.sourcegitcommit: 7e9380e53341755df13fce130ab3287918a8e44c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2018
---
# <a name="performance-center-for-sql-server-database-engine-and-azure-sql-database"></a>SQL Server 数据库引擎和 Azure SQL 数据库的性能中心
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
本页提供的链接可帮助你找到有关 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 和 [!INCLUDE[ssSDSFull](../../includes/sssdsfull-md.md)]中的性能的必要信息。  
  
 **图例**  
  
 ![security-center-legend](../../relational-databases/performance/media/security-center-legend.PNG "security-center-legend")  
  
## <a name="this-is-a-work-in-process-does-this-performance-center-help-you-how-can-we-improve-it"></a>这是正在进行中的工作。 此性能中心对你是否有帮助？ 我们可以如何改进它？  
 你正在查找哪些信息，是否已经找到？ 有哪些我们遗漏了的方面？ 你希望在此看到什么内容？ 我们不断听取你的反馈来改进内容。 请将你的意见提交到 [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com?subject=Your%20feedback%20about%20the%20Temporal%20Tables%20page)  
  
## <a name="configuration-options-for-performance"></a>性能的配置选项  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 通过许多 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 级别的配置选项，提供了可影响数据库引擎性能的功能。 通过 [!INCLUDE[ssSDSFull](../../includes/sssdsfull-md.md)]，Microsoft 可为你执行这些优化中的大多数（不是全部）。  
  
|||  
|-|-|  
|**磁盘配置选项**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [磁盘条带化和 RAID](https://technet.microsoft.com/library/ms190764\(v=sql.105\).aspx)|  
|**数据和日志文件配置选项**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [将数据和日志文件放到不同的驱动器上](../../relational-databases/policy-based-management/place-data-and-log-files-on-separate-drives.md)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [查看或更改数据文件和日志文件的默认位置 &#40;SQL Server Management Studio&#41;](../../database-engine/configure-windows/view-or-change-the-default-locations-for-data-and-log-files.md)|  
|**TempDB 配置选项**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [TempDB 的性能提高](https://msdn.microsoft.com/library/ms190768.aspx#Anchor_1)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [数据库引擎配置 - TempDB](http://msdn.microsoft.com/library/7aabd304-f3c9-4c2d-bf9d-5479ee2498da)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [Using SSDs in Azure VMs to store SQL Server TempDB and Buffer Pool Extensions](http://blogs.technet.com/b/dataplatforminsider/archive/2014/09/25/using-ssds-in-azure-vms-to-store-sql-server-tempdb-and-buffer-pool-extensions.aspx)（使用 Azure VM 中的 SSD 存储 SQL Server TempDB 和缓冲池扩展）<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [Azure 虚拟机中 SQL Server 的临时磁盘的磁盘和性能最佳实践](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-performance-best-practices/)|  
|**服务器配置选项**|<ul><li>**处理器配置选项**<br /><br /> <ul><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“关联掩码”服务器配置选项](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“关联 I/O 掩码”服务器配置选项](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“Affinity64 掩码”服务器配置选项](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“Affinity64 I/O 掩码”服务器配置选项](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“最大工作线程”服务器配置选项](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)</li></ul></li><li>**内存配置选项**<br /><br /> <ul><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“服务器内存”服务器配置选项](../../database-engine/configure-windows/server-memory-server-configuration-options.md)</li></ul></li><li>**索引配置选项**<br /><br /> <ul><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“填充因子”服务器配置选项](../../database-engine/configure-windows/configure-the-fill-factor-server-configuration-option.md)</li></ul></li><li>**查询配置选项**<br /><br /> <ul><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“每次查询占用的最小内存”服务器配置选项](../../database-engine/configure-windows/configure-the-min-memory-per-query-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“查询调控器开销限制”服务器配置选项](../../database-engine/configure-windows/configure-the-query-governor-cost-limit-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“最大并行度”服务器配置选项](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [配置“并行的开销阈值”服务器配置选项](../../database-engine/configure-windows/configure-the-cost-threshold-for-parallelism-server-configuration-option.md)</li><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [“针对即席工作负荷进行优化”服务器配置选项](../../database-engine/configure-windows/optimize-for-ad-hoc-workloads-server-configuration-option.md)</li></ul></li><li>**备份配置选项**<br /><br /> <ul><li>![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [查看或配置“备份压缩默认值”服务器配置选项](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)</li></ul></li></ul>|  
|**数据库配置优化选项**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [数据压缩](../../relational-databases/data-compression/data-compression.md)<br />![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [查看或更改数据库的兼容级别](../../relational-databases/databases/view-or-change-the-compatibility-level-of-a-database.md)<br />![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)|  
|**表配置优化**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [已分区表和已分区索引](../../relational-databases/partitions/partitioned-tables-and-indexes.md)|  
|**Azure 虚拟机中的数据库引擎性能**|![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [快速检查列表](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-performance-best-practices/)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [虚拟机大小和存储帐户注意事项](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-sql-server-performance-best-practices/)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [磁盘和性能注意事项](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-performance-best-practices/)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [I/O 性能注意事项](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-sql-server-performance-best-practices/)<br />![security-center-sqlserver](../../relational-databases/performance/media/security-center-sqlserver.png "security-center-sqlserver") [功能特定的性能注意事项](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-performance-best-practices/)|  
  
## <a name="query-performance-options"></a>查询性能选项  
  
|||  
|-|-|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [索引](../../relational-databases/indexes/indexes.md)|[重新组织和重新生成索引](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md)<br />[为索引指定填充因子](../../relational-databases/indexes/specify-fill-factor-for-an-index.md)<br />[配置并行索引操作](../../relational-databases/indexes/configure-parallel-index-operations.md)<br />[用于索引的 SORT_IN_TEMPDB 选项](../../relational-databases/indexes/sort-in-tempdb-option-for-indexes.md)<br />[改进全文索引的性能](../../relational-databases/search/improve-the-performance-of-full-text-indexes.md)<br />[配置“每次查询占用的最小内存”服务器配置选项](../../database-engine/configure-windows/configure-the-min-memory-per-query-server-configuration-option.md)<br />[Configure the index create memory Server Configuration Option](../../database-engine/configure-windows/configure-the-index-create-memory-server-configuration-option.md)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [已分区表和已分区索引](../../relational-databases/partitions/partitioned-tables-and-indexes.md)|[分区的优点](https://msdn.microsoft.com/library/ms190787.aspx#Anchor_0)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") **[联接](../../relational-databases/performance/joins.md)**|[联接基础知识](../../relational-databases/performance/joins.md#fundamentals)<br />[嵌套循环联接](../../relational-databases/performance/joins.md#nested_loops)<br />[合并联接](../../relational-databases/performance/joins.md#merge)<br />[联接](../../relational-databases/performance/joins.md#hash)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") **[子查询](../../relational-databases/performance/subqueries.md)**|[子查询基础知识](../../relational-databases/performance/subqueries.md#fundamentals)<br />[相关子查询](../../relational-databases/performance/subqueries.md#correlated)<br />[子查询类型](../../relational-databases/performance/subqueries.md#types)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [存储过程](../stored-procedures/stored-procedures-database-engine.md)|[CREATE PROCEDURE (Transact-SQL)](../../t-sql/statements/create-procedure-transact-sql.md#best-practices)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [用户定义函数](../user-defined-functions/user-defined-functions.md)|[CREATE FUNCTION (Transact-SQL)](../../t-sql/statements/create-function-transact-sql.md#best-practices)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") **并行优化**|[配置 max worker threads 服务器配置选项](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)<br />[ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") **查询优化器优化**|[ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both") [统计信息](../../relational-databases/statistics/statistics.md)|[何时更新统计信息](https://msdn.microsoft.com/library/ms190397.aspx#Anchor_3)<br />[更新统计信息](../../relational-databases/statistics/update-statistics.md)|  
|![security-center-both](../../relational-databases/performance/media/security-center-both.png "security-center-both")  **[内存中 OLTP（内存中优化）](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)**|[Memory-Optimized Tables](../../relational-databases/in-memory-oltp/memory-optimized-tables.md)<br />[本机编译的存储过程](../../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md)<br />[通过本机编译的存储过程创建和访问 TempDB 中的表](../../relational-databases/in-memory-oltp/create-and-access-tables-in-tempdb-from-stored-procedures.md)<br />[对内存优化哈希索引的常见性能问题进行故障排除](http://msdn.microsoft.com/library/1954a997-7585-4713-81fd-76d429b8d095)<br />[演示：内存中 OLTP 的性能改进](../../relational-databases/in-memory-oltp/demonstration-performance-improvement-of-in-memory-oltp.md)|  
  
## <a name="see-also"></a>另请参阅  
 [监视和优化性能](../../relational-databases/performance/monitor-and-tune-for-performance.md)   
 [相关视图、函数和过程](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)   
 [单一数据库的 Azure SQL 数据库性能指南](https://azure.microsoft.com/documentation/articles/sql-database-performance-guidance/)   
 [使用弹性池优化 Azure SQL 数据库性能](https://azure.microsoft.com/documentation/articles/sql-database-elastic-pool-guidance/)   
 [Azure 查询性能见解](https://azure.microsoft.com/documentation/articles/sql-database-query-performance/)  
 [索引设计指南](../../relational-databases/sql-server-index-design-guide.md)  
 [内存管理体系结构指南](../../relational-databases/memory-management-architecture-guide.md)  
 [页和区体系结构指南](../../relational-databases/pages-and-extents-architecture-guide.md)  
 [迁移后验证和优化指南](../../relational-databases/post-migration-validation-and-optimization-guide.md)  
 [查询处理体系结构指南](../../relational-databases/query-processing-architecture-guide.md)  
 [SQL Server 事务锁定和行版本控制指南](https://msdn.microsoft.com/library/jj856598)  
 [SQL Server 事务日志体系结构和管理指南](../../relational-databases/sql-server-transaction-log-architecture-and-management-guide.md)  
 [线程和任务体系结构指南](../../relational-databases/thread-and-task-architecture-guide.md) 
  
