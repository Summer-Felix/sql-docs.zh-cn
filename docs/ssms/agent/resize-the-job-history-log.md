---
title: "调整作业历史记录日志的大小 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-agent
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c04ed3df42c5dc14580e5343b876989144b97d1e
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="resize-the-job-history-log"></a>Resize the Job History Log
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] 本主题介绍如何使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] 设置 [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理作业历史记录日志的大小限制。
  
-   **开始之前：**  
  
    [Security](#Security)  
  
-   **若要设置作业历史记录日志的大小限制，可使用：**  
  
    [SQL Server Management Studio](#SSMS)  
  
## <a name="BeforeYouBegin"></a>开始之前  
  
### <a name="Security"></a>Security  
有关详细信息，请参阅 [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md)。  
  
## <a name="SSMS"></a>使用 SQL Server Management Studio  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a>基于原始大小调整作业历史记录日志的大小  
  
1.  在 **“对象资源管理器”** 中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]的实例，然后展开该实例。  
  
2.  右键单击“SQL Server 代理”，然后单击“属性”。  
  
3.  选择“历史记录”页，然后确认已选中“限制作业历史记录日志的大小”。  
  
4.  在 **“作业历史记录日志的最大大小”** 框中，输入作业历史记录日志允许的最大行数。  
  
5.  在 **“每个作业的最大作业历史记录行数”** 框中，输入作业允许的作业历史记录的最大行数。  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a>基于时间调整作业历史记录日志的大小  
  
1.  在 **对象资源管理器**中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]的实例，然后展开该实例。  
  
2.  右键单击“SQL Server 代理”，然后单击“属性”。  
  
3.  选择 **“历史记录”** 页，然后单击 **“自动删除代理历史记录”**。  
  
4.  选择适当的“天”、“周”或“月”数。  
  
