---
title: "创建作业类别 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-agent
ms.reviewer: 
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0d1809cc9170cc0213d52dc4b96b75e44e9e05af
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="create-a-job-category"></a>创建作业类别
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
本主题介绍如何使用 [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] 、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)]或 [!INCLUDE[tsql](../../includes/tsql_md.md)] 管理对象在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 中创建作业类别。  
  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理提供了内置作业类别，可以向这些类别分配作业，也可以创建作业类别并对其分配作业。 作业类别有助于您组织作业，从而更容易筛选和分组。 例如，可以将所有数据库备份作业组织到“数据库维护”类别中。 此外，还可以创建自己的作业类别。  
  
**本主题内容**  
  
-   **开始之前：**  
  
    [限制和局限](#Restrictions)  
  
    [Security](#Security)  
  
-   **若要创建作业类别，可使用：**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server 管理对象](#SMO)  
  
## <a name="BeforeYouBegin"></a>开始之前  
  
### <a name="Restrictions"></a>限制和局限  
多服务器类别仅存在于主服务器上。 主服务器上仅提供了一个默认作业类别：“[未分类(多服务器)]”。 下载多服务器作业后，其类别将在目标服务器上更改为“来自 MSX 的作业”  。  
  
### <a name="Security"></a>Security  
有关详细信息，请参阅 [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md)。  
  
## <a name="SSMS"></a>使用 SQL Server Management Studio  
  
#### <a name="to-create-a-job-category"></a>创建作业类别  
  
1.  在 **“对象资源管理器”**中，单击加号以展开您想要在其中创建作业类别的服务器。  
  
2.  单击加号以展开 **“SQL Server 代理”**。  
  
3.  右键单击 **“作业”** 文件夹，然后选择 **“管理作业类别”**。  
  
4.  在“管理作业类别server_name” 对话框中，单击“添加”。  
  
5.  在新对话框的 **“名称”** 框中，输入新作业类别的名称。  
  
6.  选中 **“显示所有作业”** 复选框。 通过选中作业对应的框来为新类别选择一个或多个作业。  
  
7.  单击“确定” 。  
  
8.  在“管理作业类别server_name” 对话框中，单击“刷新”，确保新的作业类别处于活动状态。 如果一切都与预期情况相同，则关闭此对话框。  
  
有关这些对话框的详细信息，请参阅 [作业类别 - 管理作业类别](../../ssms/agent/job-categories-manage-job-categories.md) 和 [作业类别属性 - 新建作业类别](../../ssms/agent/job-categories-properties-new-job-category.md)。  
  
## <a name="TSQL"></a>使用 Transact-SQL  
  
#### <a name="to-create-a-job-category"></a>创建作业类别  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDE](../../includes/ssde_md.md)]的实例。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击“执行” 。  
  
    ```  
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
有关详细信息，请参阅 [sp_add_category (Transact-SQL)](http://msdn.microsoft.com/en-us/6cca32cd-d941-4378-aed6-a7c90cb7520a)。  
  
## <a name="SMO"></a>使用 SQL Server 管理对象  
**创建作业类别**  
  
通过使用所选编程语言（如 Visual Basic、Visual C# 或 PowerShell）来调用 **JobCategory** 类。 有关示例代码，请参阅 [在 SQL Server 代理中计划自动管理任务](http://msdn.microsoft.com/en-us/900242ad-d6a2-48e9-8a1b-f0eea4413c16)。  
  
