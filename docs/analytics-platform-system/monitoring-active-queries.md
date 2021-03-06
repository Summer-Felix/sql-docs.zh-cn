---
title: "监视活动查询 (SQL Server PDW)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/13/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bb73f790-0537-414b-8dc2-f1eb69b92362
caps.latest.revision: "7"
ms.openlocfilehash: 44f128124c8027bf4c37e34309d6c711006ac113
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="monitoring-active-queries"></a>监视活动查询
本主题演示如何使用管理控制台和 SQL Server PDW 系统视图来监视活动查询。 请参阅[通过使用管理控制台监视设备](monitor-the-appliance-by-using-the-admin-console.md)和[系统视图](tsql-system-views.md)有关这些工具的信息。  
  
## <a name="prerequisites"></a>必备条件  
无论哪种方法，用于监视活动查询，该登录名必须具有"使用所有的管理控制台"中描述的权限[授予权限以使用管理控制台](grant-permissions.md#grant-permissions-to-use-the-admin-console)。  
  
## <a name="PermsAdminConsole"></a>监视器活动查询  
管理员控制台和 SQL Server PDW 系统视图可以用于监视活动查询。 按照下面的说明。  
  
### <a name="to-monitor-active-queries-by-using-the-admin-console"></a>通过使用管理控制台中监视活动查询  
  
1.  登录到管理员控制台。 请参阅[通过使用管理控制台监视设备](monitor-the-appliance-by-using-the-admin-console.md)有关的说明。  
  
2.  在顶部菜单中，单击**查询**。 设备，包括登录名，提交查询、 查询和查询的当前状态的开始和结束时间上，将看到有关最新的查询的基本信息的表。  
  
3.  若要查看查询命令，请将鼠标指针悬停该行左侧列中的查询 ID。  
  
    若要查看有关特定查询的更多详情，请单击查询 id。 你将看到包括完整的查询和查询计划，在查询执行中的每个步骤的状态信息的信息。 如果未返回任何错误，还可以在错误上查看详细的信息。 <!-- MISSING LINKS See [Understanding Query Plans &#40;SQL Server PDW&#41;](../sqlpdw/understanding-query-plans-sql-server-pdw.md) for information on how to interpret the query plan information available in the Admin Console.  -->
  
### <a name="to-monitor-active-queries-by-using-the-system-views"></a>通过使用系统视图中监视活动查询  
用于监视查询的主系统视图是[sys.dm_pdw_exec_requests](../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)。 使用此系统视图来查找`request_id`对于活动或新的查询，基于查询文本。  
  
例如，下面的查询查找`request_id`和当前`status`任何选择查询的中的所有列`memberAddresses`表。  
  
```sql  
SELECT request_id, command, status   
FROM sys.dm_pdw_exec_requests   
WHERE command   
LIKE ‘%SELECT * FROM db1..memberAddresses%’;  
```  
  
后`request_id`已被标识为查询，使用中的其他信息`dm_pdw_exec_requests`表若要了解有关处理的查询，或使用[sys.dm_pdw_request_steps](../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)查看单个查询的状态查询执行的步骤。  
  
<!-- MISSING LINKS 
## See Also  
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  
-->
  
