---
title: "定义合并表项目间的逻辑记录关系 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "合并复制逻辑记录 [SQL Server 复制]"
  - "项目 [SQL Server 复制], 逻辑记录"
  - "逻辑记录 [SQL Server 复制]"
ms.assetid: ff847b3a-c6b0-4eaf-b225-2ffc899c5558
caps.latest.revision: 44
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 44
---
# 定义合并表项目间的逻辑记录关系
  本主题说明如何使用 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]、[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 或复制管理对象 (RMO) 在 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 中定义合并表项目间的逻辑记录关系。  
  
 通过使用合并复制，您可以定义不同表中的相关行之间的关系。 然后就可以在同步过程中将这些行作为一个事务单元进行处理。 无论两个项目之间是否存在联接筛选器关系，都可以在这两个项目之间定义逻辑记录。 有关详细信息，请参阅 [通过逻辑记录对相关行组更改](../../../relational-databases/replication/merge/group-changes-to-related-rows-with-logical-records.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [限制和局限](#Restrictions)  
  
-   **定义合并表项目间的逻辑记录关系，使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [复制管理对象 (RMO)](#RMOProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Restrictions"></a> 限制和局限  
  
-   如果在初始化对发布的订阅后添加、修改或删除逻辑记录，必须在更改后生成新的快照并重新初始化所有订阅。 有关属性更改要求的详细信息，请参阅 [更改发布和项目属性](../../../relational-databases/replication/publish/change-publication-and-article-properties.md)。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
 定义逻辑记录中的 **添加联接** 对话框中，可以在新建发布向导和 **发布属性-\< 发布>** 对话框。 有关使用向导和访问对话框中的详细信息，请参阅 [创建发布](../../../relational-databases/replication/publish/create-a-publication.md) 和 [查看和修改发布属性](../../../relational-databases/replication/publish/view-and-modify-publication-properties.md)。  
  
 仅当逻辑记录应用于合并发布中的联接筛选器且发布遵循使用预计算分区的要求时，才可以在 **“添加联接”** 对话框中定义逻辑记录。 若要定义不应用于联接筛选器的逻辑记录并在逻辑记录级设置冲突检测和解决方法，必须使用存储过程。  
  
#### 定义逻辑记录关系  
  
1.  在 **筛选表行** 新建发布向导的页面或 **筛选行** 页 **发布属性-\< 发布>** 对话框中，选择一个行筛选器在 **筛选的表** 窗格。  
  
     逻辑记录关系与扩展行筛选器的联接筛选器相关联。 因此，必须定义一个行筛选器，才能用联接来扩展该筛选器并应用逻辑记录关系。 定义一个联接筛选器后，可使用其他联接筛选器来扩展此联接筛选器。 有关定义联接筛选器的详细信息，请参阅 [Define and Modify a Join Filter Between Merge Articles](../../../relational-databases/replication/publish/define-and-modify-a-join-filter-between-merge-articles.md)。  
  
2.  单击 **“添加”**，再单击 **“添加联接以扩展所选筛选器”**。  
  
3.  在 **“添加联接”** 对话框中定义一个联接筛选器，然后选中 **“逻辑记录”**复选框。  
  
4.  如果您在 **发布属性-\< 发布>** 对话框中，单击 **确定** 以保存并关闭对话框。  
  
#### 删除逻辑记录关系  
  
-   只删除逻辑记录关系，或者删除逻辑记录关系及其相关联的联接筛选器。  
  
     只删除逻辑记录关系：  
  
    1.  在 **筛选行** 新建发布向导的页面或 **筛选行** 页 **发布属性-\< 发布>** 对话框中，选择与中的逻辑记录关系相关联的联接筛选器 **筛选的表** 窗格中，然后再单击 **编辑**。  
  
    2.  在 **“编辑联接”** 对话框中，清除 **“逻辑记录”**复选框。  
  
    3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     删除逻辑记录关系及其相关联的联接筛选器：  
  
    -   在 **筛选行** 新建发布向导的页面或 **发布属性-\< 发布>** 对话框中选择筛选器 **筛选的表** 窗格中，然后再单击 **删除**。 如果删除的联接筛选器自身是由其他联接扩展而成的，则也将删除那些联接。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
 您可以使用复制存储过程以编程方式指定项目之间的逻辑记录关系。  
  
#### 在没有关联的联接筛选器的情况下定义逻辑记录关系  
  
1.  如果该发布包含筛选任何项目，则执行 [sp_helpmergepublication](../../../relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql.md), ，并记下的值 **use_partition_groups** 结果集中。  
  
    -   如果值为 **1**，则已使用预计算分区。  
  
    -   如果值为 **0**, ，然后执行 [sp_changemergepublication](../../../relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql.md) 发布服务器上对发布数据库。 将值指定为 **use_partition_groups** 为 **@property** ，值为 **true** 为 **@value**。  
  
        > [!NOTE]  
        >  如果发布不支持预计算分区，则无法使用逻辑记录。 有关详细信息，请参阅使用预计算分区的要求主题 [使用预计算分区优化参数化筛选器性能](../../../relational-databases/replication/merge/optimize-parameterized-filter-performance-with-precomputed-partitions.md)。  
  
    -   如果值为 NULL，则需要运行快照代理以生成发布的初始快照。  
  
2.  如果将包含逻辑记录的文章不存在，则执行 [sp_addmergearticle](../../../relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql.md) 发布服务器上对发布数据库。 为逻辑记录指定以下冲突检测和解决选项中的一项：  
  
    -   若要检测和解决在逻辑记录中的相关行中发生的冲突，将值指定为 **true** 为 **@logical_record_level_conflict_detection** 和 **@logical_record_level_conflict_resolution**。  
  
    -   若要使用的标准的行或列级冲突检测和解决方法，将值指定为 **false** 为 **@logical_record_level_conflict_detection** 和 **@logical_record_level_conflict_resolution**, ，这是默认设置。  
  
3.  为每个将包含逻辑记录的项目重复步骤 2。 您必须为逻辑记录中的每个项目使用相同的冲突检测和解决选项。 有关详细信息，请参阅 [Detecting and Resolving Conflicts in Logical Records](../../../relational-databases/replication/merge/detecting-and-resolving-conflicts-in-logical-records.md)。  
  
4.  在发布服务器上对发布数据库中，执行 [sp_addmergefilter](../../../relational-databases/system-stored-procedures/sp-addmergefilter-transact-sql.md)。 指定 **@publication**, ，为关系中的一个项目的名称 **@article**, ，第二个项目的名称 **@join_articlename**, 的关系的名称 **@filtername**, ，用于定义两者之间的关系的子句文章为 **@join_filterclause**, 的联接类型 **@join_unique_key** 以及下列其中一项值为 **@filter_type**:  
  
    -   **2** -定义逻辑关系。  
  
    -   **3** -与联接筛选器定义的逻辑关系。  
  
    > [!NOTE]  
    >  如果未使用联接筛选器，则两个项目之间的关系方向并不重要。  
  
5.  为发布中剩余的每个逻辑记录关系重复步骤 2。  
  
#### 为逻辑记录更改冲突检测和解决方法  
  
1.  检测和解决发生在逻辑记录中相关行之间的冲突：  
  
    -   在发布服务器上对发布数据库中，执行 [sp_changemergearticle](../../../relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql.md)。 将值指定为 **logical_record_level_conflict_detection** 为 **@property** ，值为 **true** 为 **@value**。 将值指定为 **1** 为 **@force_invalidate_snapshot** 和 **@force_reinit_subscription**。  
  
    -   在发布服务器上对发布数据库中，执行 [sp_changemergearticle](../../../relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql.md)。 将值指定为 **logical_record_level_conflict_resolution** 为 **@property** ，值为 **true** 为 **@value**。 将值指定为 **1** 为 **@force_invalidate_snapshot** 和 **@force_reinit_subscription**。  
  
2.  使用标准行级或列级冲突检测和解决方法：  
  
    -   在发布服务器上对发布数据库中，执行 [sp_changemergearticle](../../../relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql.md)。 将值指定为 **logical_record_level_conflict_detection** 为 **@property** ，值为 **false** 为 **@value**。 将值指定为 **1** 为 **@force_invalidate_snapshot** 和 **@force_reinit_subscription**。  
  
    -   在发布服务器上对发布数据库中，执行 [sp_changemergearticle](../../../relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql.md)。 将值指定为 **logical_record_level_conflict_resolution** 为 **@property** ，值为 **false** 为 **@value**。 将值指定为 **1** 为 **@force_invalidate_snapshot** 和 **@force_reinit_subscription**。  
  
#### 删除逻辑记录关系  
  
1.  在发布服务器上，对发布数据库执行以下查询，以返回有关为指定的发布定义的所有逻辑记录关系的信息：  
  
     [!code-sql[HowTo#sp_ReturnMergeLogicalRecords](../../../relational-databases/replication/codesnippet/tsql/define-a-logical-record-_1.sql)]  
  
     注意在结果集 **filtername** 列中的被删除逻辑记录关系的名称。  
  
    > [!NOTE]  
    >  此查询将返回相同的信息 [sp_helpmergefilter](../../../relational-databases/system-stored-procedures/sp-helpmergefilter-transact-sql.md); 但是，此系统存储过程仅返回有关逻辑记录关系的信息还联接筛选器。  
  
2.  在发布服务器上对发布数据库中，执行 [sp_dropmergefilter](../../../relational-databases/system-stored-procedures/sp-dropmergefilter-transact-sql.md)。 指定 **@publication**，为 **@article**指定该关系中其中一个项目的名称，并为 **@filtername**指定步骤 1 中的关系的名称。  
  
###  <a name="TsqlExample"></a> 示例 (Transact-SQL)  
 此示例对现有发布启用预计算分区，并创建包含 `SalesOrderHeader` 和 `SalesOrderDetail` 表的两个新项目的逻辑记录。  
  
 [!code-sql[HowTo#sp_AddMergeLogicalRecord](../../../relational-databases/replication/codesnippet/tsql/define-a-logical-record-_2.sql)]  
  
##  <a name="RMOProcedure"></a> 使用复制管理对象 (RMO)  
  
> [!NOTE]  
>  利用合并复制，您可以指定在逻辑记录级跟踪和解决冲突，但使用 RMO 却无法设置这些选项。  
  
#### 在没有关联的联接筛选器的情况下定义逻辑记录关系  
  
1.  通过使用创建连接到发布服务器 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类。  
  
2.  创建的实例 <xref:Microsoft.SqlServer.Replication.MergePublication> 类中，设置 <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> 和 <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> 属性的发布，并设置 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为在步骤 1 中创建的连接。  
  
3.  调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法以获取该对象的属性。 如果此方法返回 **false**，则说明步骤 2 中的发布属性定义不正确，或者此发布不存在。  
  
4.  如果 <xref:Microsoft.SqlServer.Replication.MergePublication.PartitionGroupsOption%2A> 属性设置为 <xref:Microsoft.SqlServer.Replication.PartitionGroupsOption.False>, ，将其设置为 <xref:Microsoft.SqlServer.Replication.PartitionGroupsOption.True>。  
  
5.  如果要构成逻辑记录的文章不存在，则创建的实例 <xref:Microsoft.SqlServer.Replication.MergeArticle> 类，并设置以下属性︰  
  
    -   项目的名称 <xref:Microsoft.SqlServer.Replication.Article.Name%2A>。  
  
    -   有关发布的名称 <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>。  
  
    -   （可选）如果对项目进行水平筛选，指定的行筛选器子句 <xref:Microsoft.SqlServer.Replication.MergeArticle.FilterClause%2A> 属性。 使用此属性可指定静态行筛选器或参数化行筛选器。 有关详细信息，请参阅 [Parameterized Row Filters](../../../relational-databases/replication/merge/parameterized-row-filters.md)。  
  
     有关详细信息，请参阅 [Define an Article](../../../relational-databases/replication/publish/define-an-article.md)。  
  
6.  调用 <xref:Microsoft.SqlServer.Replication.Article.Create%2A> 方法。  
  
7.  对构成逻辑记录的每个项目，重复执行步骤 5 和 6。  
  
8.  创建的实例 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter> 类来定义项目之间的逻辑记录关系。 然后，设置以下属性：  
  
    -   为逻辑记录关系中的子项目的名称 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter.ArticleName%2A> 属性。  
  
    -   为逻辑记录关系中现有的父项目的名称 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter.JoinArticleName%2A> 属性。  
  
    -   为逻辑记录关系的名称 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter.FilterName%2A> 属性。  
  
    -   定义的关系的表达式 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter.JoinFilterClause%2A> 属性。  
  
    -   值为 <xref:Microsoft.SqlServer.Replication.FilterTypes.LogicalRecordLink> 为 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter.FilterTypes%2A> 属性。 如果逻辑记录关系也是联接筛选器，将值指定为 <xref:Microsoft.SqlServer.Replication.FilterTypes.JoinFilterAndLogicalRecordLink> 此属性。 有关详细信息，请参阅 [通过逻辑记录对相关行组更改](../../../relational-databases/replication/merge/group-changes-to-related-rows-with-logical-records.md)。  
  
9. 调用 <xref:Microsoft.SqlServer.Replication.MergeArticle.AddMergeJoinFilter%2A> 方法表示关系中的子项目的对象。 传递 <xref:Microsoft.SqlServer.Replication.MergeJoinFilter> 步骤 8 以定义的关系中的对象。  
  
10. 对发布中的其余每个逻辑记录关系重复执行步骤 8 和 9。  
  
###  <a name="PShellExample"></a> 示例 (RMO)  
 此示例为 `SalesOrderHeader` 和 `SalesOrderDetail` 表创建一个由两个新项目构成的逻辑记录。  
  
 [!code-csharp[HowTo#rmo_CreateLogicalRecord](../../../relational-databases/replication/codesnippet/csharp/rmohowto/rmotestevelope.cs#rmo_createlogicalrecord)]  
  
 [!code-vb[HowTo#rmo_vb_CreateLogicalRecord](../../../relational-databases/replication/codesnippet/visualbasic/rmohowtovb/rmotestenv.vb#rmo_vb_createlogicalrecord)]  
  
## 另请参阅  
 [定义和修改合并项目间的联接筛选器](../../../relational-databases/replication/publish/define-and-modify-a-join-filter-between-merge-articles.md)   
 [定义和修改合并项目的参数化行筛选器](../../../relational-databases/replication/publish/define-and-modify-a-parameterized-row-filter-for-a-merge-article.md)   
 [定义和修改静态行筛选器](../../../relational-databases/replication/publish/define-and-modify-a-static-row-filter.md)   
 [通过逻辑记录对相关行的更改进行分组](../../../relational-databases/replication/merge/group-changes-to-related-rows-with-logical-records.md)   
 [使用预计算分区优化参数化筛选器的性能](../../../relational-databases/replication/merge/optimize-parameterized-filter-performance-with-precomputed-partitions.md)   
 [通过逻辑记录对相关行的更改进行分组](../../../relational-databases/replication/merge/group-changes-to-related-rows-with-logical-records.md)  
  
  