---
title: "联机索引操作准则 | Microsoft Docs"
ms.custom: ""
ms.date: "03/09/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-indexes"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "聚集索引, 联机操作"
  - "联机索引操作"
  - "索引 [SQL Server], 联机操作"
  - "磁盘空间 [SQL Server], 索引"
  - "非聚集索引 [SQL Server], 联机操作"
  - "事务日志 [SQL Server], 索引"
ms.assetid: d82942e0-4a86-4b34-a65f-9f143ebe85ce
caps.latest.revision: 64
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 60
---
# 联机索引操作准则
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  执行联机索引操作时，请按照下列指南进行：  
  
-   如果基础表包含下列大型对象 (LOB) 数据类型： **image**、 **ntext**和 **text**，则必须脱机创建、重新生成或删除聚集索引。  
  
-   如果表包含 LOB 数据类型，但索引定义中未使用这些列中的任何列作为键或非键（包含性）列，则可以联机创建非唯一的非聚集索引。  
  
-   无法为本地临时表联机创建、重新生成或删除索引。 全局临时表的索引则没有此限制。  
  
> [!NOTE]  
>  在 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的各版本中均不提供联机索引操作。 有关 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]各版本支持的功能列表，请参阅 [SQL Server 2016 各个版本支持的功能](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md)。  
  
 下表显示了可以联机执行的索引操作以及不能联机操作的索引。 其中还包括其他限制。  
  
|联机索引操作|不能执行联机操作的索引|其他限制|  
|----------------------------|----------------------|------------------------|  
|ALTER INDEX REBUILD|禁用的聚集索引或禁用的索引视图<br /><br /> XML 索引<br /><br />列存储索引 <br /><br /> 对本地临时表的索引|当表中包含不能执行联机操作的索引时，指定关键字 ALL 可能会导致操作失败。<br /><br /> 有关重新生成禁用索引的其他限制。 有关详细信息，请参阅 [禁用索引和约束](../../relational-databases/indexes/disable-indexes-and-constraints.md)。|  
|CREATE INDEX|XML 索引<br /><br /> 视图的初始唯一聚集索引<br /><br /> 对本地临时表的索引||  
|CREATE INDEX WITH DROP_EXISTING|禁用的聚集索引或禁用的索引视图<br /><br /> 对本地临时表的索引<br /><br /> XML 索引||  
|DROP INDEX|已禁用的索引<br /><br /> XML 索引<br /><br /> 非聚集索引<br /><br /> 对本地临时表的索引|无法在一条语句中指定多个索引。|  
|ALTER TABLE ADD CONSTRAINT（PRIMARY KEY 或 UNIQUE 约束）|对本地临时表的索引<br /><br /> 聚集索引|每次只允许一个子句。 例如，无法在同一个 ALTER TABLE 语句中添加和删除 PRIMARY KEY 或 UNIQUE 约束。|  
|ALTER TABLE DROP CONSTRAINT（PRIMARY KEY 或 UNIQUE 约束）|聚集索引||  
  
 在联机索引操作过程中，不能修改、截断或删除基础表。  
  
 在创建或删除聚集索引时指定的联机选项设置（ON 或 OFF）适用于任何必须重新生成的非聚集索引。 例如，如果聚集索引是使用 CREATE INDEX WITH DROP_EXISTING、ONLINE=ON 联机生成的，则所有关联的非聚集索引也将联机重新生成。  
  
 联机创建或重新生成 UNIQUE 索引时，索引生成器和并发用户事务可能会尝试插入相同的键，从而违反唯一性。 如果在源表中的原始行移至新的索引之前，用户输入的行插入到了新的索引（目标），则联机索引操作将失败。  
  
 虽然并不常见，但联机索引操作在与数据库更新进行交互时会因为用户或应用程序的活动而导致死锁。 在这些少数情况下， [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 会选择用户或应用程序活动作为死锁牺牲品。  
  
 只有在创建多个新的非聚集索引或重新组织非聚集索引时，才能对同一个表或视图执行并发联机索引 DDL 操作。 同一时间执行的所有其他联机索引操作都将失败。 例如，对同一个表联机重新生成现有的索引时，不能联机创建新的索引。  
  
 索引包含一列大型对象类型，且在同一事务中在联机操作前存在更新操作时，不能执行此联机操作。 要解决这个问题，请将联机操作放在事务外部或将它放在事务中所有更新操作之前。  
  
## <a name="disk-space-considerations"></a>磁盘空间注意事项  
 通常，联机索引操作和脱机索引操作对磁盘空间的要求相同。 一种例外情况是，临时映射索引需要更多的磁盘空间。 此临时索引是在联机索引操作（创建、重新生成或删除聚集索引）中使用的。 删除联机聚集索引与创建联机聚集索引需要的空间同样多。 有关详细信息，请参阅 [Disk Space Requirements for Index DDL Operations](../../relational-databases/indexes/disk-space-requirements-for-index-ddl-operations.md)。  
  
## <a name="performance-considerations"></a>性能注意事项  
 虽然联机索引操作允许进行并发的用户更新活动，但如果更新活动量很大，索引操作将花费较长的时间。 通常，无论并发更新活动的级别如何，联机索引操作都将比相应的脱机索引操作更慢。  
  
 由于源结构和目标结构都是在联机索引操作过程中维护的，则插入、更新和删除事务所使用的资源会增加，有可能会增长一倍。 这会导致在索引操作过程中性能降低和使用较多的资源，尤其是 CPU 时间。 联机索引操作将完整记入日志。  
  
 尽管建议联机操作，但仍应评估环境和特定的需要是否满足。 脱机执行索引操作可能是最好的。 这样做可能会在操作过程中限制用户对数据的访问，但是操作将更快地完成并使用较少的资源。  
  
 在运行 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]的多处理器计算机上，索引语句可能会像其他查询那样，使用多个处理器来执行与索引语句关联的扫描和排序操作。 可以使用 MAXDOP 索引选项控制专用于联机索引操作的处理器数量。 通过这种方式，可以在那些并发用户间平衡索引操作所使用的资源。 有关详细信息，请参阅 [配置并行索引操作](../../relational-databases/indexes/configure-parallel-index-operations.md)。 有关支持并行索引操作的 SQL Server 版本的详细信息，请参阅 [SQL Server 2016 各个版本支持的功能](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md)。  
  
 由于索引操作的最后阶段持有 S 锁或 Sch-M 锁，因此当在显式用户事务（例如 BEGIN TRANSACTION...COMMIT 块）内运行联机索引操作时必须小心。 此操作会造成在事务结束之前一直持有锁，从而妨碍用户并发。  
  
 若允许通过 `MAX DOP > 1` 和 `ALLOW_PAGE_LOCKS = OFF` 选项运行联机索引重新生成，可能会增加碎片。 有关详细信息，请参阅 [工作方式：联机索引重新生成 - 可能造成碎片增加](http://blogs.msdn.com/b/psssql/archive/2012/09/05/how-it-works-online-index-rebuild-can-cause-increased-fragmentation.aspx)。  
  
## <a name="transaction-log-considerations"></a>事务日志注意事项  
 脱机或联机执行大范围的索引操作，会生成大型数据负载，这些负载会造成事务日志快速填充。 为确保索引操作可以回滚，事务日志直到索引操作完成后才可以截断，但是，可以在索引操作过程中备份日志。 因此，事务日志必须具有足够的空间来存储索引操作事务和所有的并发用户事务，以满足索引操作过程的需要。 有关详细信息，请参阅 [Transaction Log Disk Space for Index Operations](../../relational-databases/indexes/transaction-log-disk-space-for-index-operations.md)。  
  
## <a name="related-content"></a>相关内容  
 [联机索引操作的工作方式](../../relational-databases/indexes/how-online-index-operations-work.md)  
  
 [联机执行索引操作](../../relational-databases/indexes/perform-index-operations-online.md)  
  
 [ALTER INDEX (Transact-SQL)](../../t-sql/statements/alter-index-transact-sql.md)  
  
 [CREATE INDEX (Transact-SQL)](../../t-sql/statements/create-index-transact-sql.md)  
  
  