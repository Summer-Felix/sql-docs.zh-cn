---
title: "更新内容 - 数据库引擎文档| Microsoft Docs"
description: "显示数据库引擎的文档中最近更改的更新内容片段。"
manager: craigg
author: MightyPen
ms.author: genemi
ms.topic: article
ms.custom: UpdArt.exe
ms.suite: sql
ms.prod_service: sql-non-specified
ms.component: database-engine
ms.date: 02/03/2018
ms.openlocfilehash: d01d9fa13342709a74d98033d093d9856ab5d680
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="new-and-recently-updated-database-engine-docs"></a>新增内容和最近更新内容：数据库引擎文档



Microsoft 几乎每天都会更新其 [Docs.Microsoft.com](http://docs.microsoft.com/) 文档网站上的一些现有文章。 本文显示从最近更新的文章中摘录的内容。 可能还会列出新文章的链接。

本文由定期重新运行的程序生成。 摘录内容偶尔会有格式问题，还可能以源文的 markdown 格式显示。 此处不会显示任何图像。

最新的更新报告涵盖以下日期范围和主题：



- 更新日期范围：2017-12-03 到 2018-02-03
- 主题区域：&nbsp;数据库引擎。




&nbsp;

## <a name="new-articles-created-recently"></a>最近创建的新文章

单击以下链接可跳转到最近添加的新文章。


暂时无新文章列出。



&nbsp;

## <a name="updated-articles-with-excerpts"></a>包含摘录内容的已更新文章

此部分摘录了最近大幅更新的文章中的更新内容。

此处显示的摘录与其对应的语义上下文脱离。 此外，有时摘录会与实际文章中此摘录周围的重要 markdown 语法元素脱离。 因此，这些摘录仅可用于一般指导。 摘录只是帮助你确定自己是否有兴趣花时间点击并访问实际文章。

鉴于以上原因及其他原因，请不要复制这些摘录中的代码，也不要将摘录当作确切事实。 请转而访问实际文章。





&nbsp;

<a name="compactupdatedlist"/>

### <a name="compact-list-of-articles-updated-recently"></a>最近更新的文章的紧凑列表

此紧凑列表中的链接指向“摘录”部分中列出的所有更新后文章。

1. [升级 Always On 可用性组副本实例](#TitleNum_1)




&nbsp;

&nbsp;

<a name="TitleNum_1"/>

### <a name="1-nbsp-upgrading-always-on-availability-group-replica-instancesavailability-groupswindowsupgrading-always-on-availability-group-replica-instancesmd"></a>1.&nbsp; [升级 Always On 可用性组副本实例](availability-groups/windows/upgrading-always-on-availability-group-replica-instances.md)

更新日期：2018-01-29 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 

<!-- Source markdown line 174.  ms.author= "mikeray".  -->

&nbsp;


<!-- git diff --ignore-all-space --unified=0 20ca282e8965889a7a530fb67e125cc876410e41 9f27d0f9a74333b291c1cdc1529edc13960fae29  (PR=4741  ,  Filename=upgrading-always-on-availability-group-replica-instances.md  ,  Dirpath=docs\database-engine\availability-groups\windows\  ,  MergeCommitSha40=0a44ce9993ebf61f86e409255a1d58d47993951a) -->



**更改数据捕获或复制的特殊步骤**


根据正在应用的更新，其他步骤可能需要 AG 副本数据库启用变更数据捕获或复制。 请参阅更新的发行说明以确定是否需要执行以下步骤：

1. 升级每个次要副本。

1. 升级所有次要副本之后，将 AG 故障转移到已升级的实例。

1. 在托管主要副本的实例上运行下列 Transact-SQL：

   ```
   EXECUTE [master].[sys].[sp_vupgrade_replication];
   ```

   >[!NOTE]
   >此命令可能需要几分钟才能运行。

1. 升级最初为主要副本的实例。

有关背景信息，请参阅[升级到最新 CU 后，CDC 功能可能会中断](http://blogs.msdn.microsoft.com/sql_server_team/cdc-functionality-may-break-after-upgrading-to-the-latest-cu-for-sql-server-2012-2014-and-2016/)。









## <a name="similar-articles-about-new-or-updated-articles"></a>新文章或更新的文章的类似文章

本节列出了 GitHub.com 公共存储库 ([MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs/)) 内其他主题区域中与最近更新的文章非常相似的文章。


#### <a name="subject-areas-that-do-have-new-or-recently-updated-articles"></a>主题区域具有新的或最近更新的文章


- [新文章和更新的文章 (1+3)：SQL&nbsp;高级分析文档](../advanced-analytics/new-updated-advanced-analytics.md)
- [新文章和更新的文章 (0+1)：SQL&nbsp;分析平台系统文档](../analytics-platform-system/new-updated-analytics-platform-system.md)
- [新文章和更新的文章 (0+1)：连接到&nbsp;SQL 文档](../connect/new-updated-connect.md)
- [新文章和更新的文章 (0+1)：SQL&nbsp;数据库引擎文档](../database-engine/new-updated-database-engine.md)
- [新文章和更新的文章 (12+1)：SQL Integration Services 文档](../integration-services/new-updated-integration-services.md)
- [新文章和更新的文章&nbsp;(6+2)：Linux for SQL 文档](../linux/new-updated-linux.md)
- [新文章和更新的文章 (15+0)：PowerShell for SQL 文档](../powershell/new-updated-powershell.md)
- [新文章和更新的文章&nbsp;(2+9)：SQL 关系数据库文档](../relational-databases/new-updated-relational-databases.md)
- [新文章和更新的文章&nbsp;(1+0)：SQL Reporting Services 文档](../reporting-services/new-updated-reporting-services.md)
- [新文章和更新的文章&nbsp;(1+1)：SQL Operations Studio 文档](../sql-operations-studio/new-updated-sql-operations-studio.md)
- [新文章和更新的文章&nbsp;(1+1)：Microsoft SQL Server 文档](../sql-server/new-updated-sql-server.md)
- [新文章和更新的文章&nbsp;(0+1)：SQL Server Data Tools (SSDT) 文档](../ssdt/new-updated-ssdt.md)
- [新文章和更新的文章&nbsp;(1+2)：SQL Server Management Studio (SSMS) 文档](../ssms/new-updated-ssms.md)
- [新文章和更新的文章&nbsp;(0+2)：Transact-SQL 文档](../t-sql/new-updated-t-sql.md)



#### <a name="subject-areas-that-do-not-have-any-new-or-recently-updated-articles"></a>主题区域没有新的或最近更新的文章


- [新文章和更新的文章 (0+0)：SQL 数据迁移助手 (DMA) 文档](../dma/new-updated-dma.md)
- [新的和更新的文章 (0+0)：ActiveX Data Objects (ADO) for SQL 文档](../ado/new-updated-ado.md)
- [新文章和更新的文章 (0+0)：SQL Analysis Services 文档](../analysis-services/new-updated-analysis-services.md)
- [新的和更新的文章 (0+0)：Data Quality Services for SQL 文档](../data-quality-services/new-updated-data-quality-services.md)
- [新的和更新的文章 (0+0)：SQL 数据挖掘扩展插件 (DMX) 文档](../dmx/new-updated-dmx.md)
- [新文章和更新的文章 (0+0)：Master Data Services (MDS) for SQL 文档](../master-data-services/new-updated-master-data-services.md)
- [新的和更新的文章 (0+0)：SQL 多维表达式 (MDX) 文档](../mdx/new-updated-mdx.md)
- [新的和更新的文章 (0+0)：SQL 开放式数据库连接 (ODBC) 文档](../odbc/new-updated-odbc.md)
- [新的和更新的文章 (0+0)：SQL 示例文档](../sample/new-updated-sample.md)
- [新的和更新的文章 (0+0)：SQL Server Migration Assistant (SSMA) 文档](../ssma/new-updated-ssma.md)
- [新文章和更新的文章 (0+0)：SQL 工具文档](../tools/new-updated-tools.md)
- [新的和更新的文章 (0+0)：XQuery for SQL 文档](../xquery/new-updated-xquery.md)


