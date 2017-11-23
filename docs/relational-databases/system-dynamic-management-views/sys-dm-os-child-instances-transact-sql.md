---
title: "sys.dm_os_child_instances (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/18/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_os_child_instances
- sys.dm_os_child_instances_TSQL
- dm_os_child_instances
- dm_os_child_instances_TSQL
dev_langs: TSQL
helpviewer_keywords:
- server state information [SQL Server]
- sys.dm_os_child_instances dynamic management view
- monitoring server health
ms.assetid: 1bef3074-0ccc-48fa-8f3d-14f3d99df86b
caps.latest.revision: "37"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d13a86c17d95f31d2ffe99fa6675a0e0fe877ecd
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmoschildinstances-transact-sql"></a>sys.dm_os_child_instances (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  为从父服务器实例创建的每个用户实例返回一行。  
  
> **重要说明！** [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 从返回的信息**sys.dm_os_child_instances**可确定每个用户实例 (heart_beat) 的状态并获取用于创建与用户的连接的管道名称 (instance_pipe_name)实例使用[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]或 SQLCmd。 只有在外部进程（例如客户端应用程序）启动了用户实例之后，您才能连接到该用户实例。 SQL 管理工具无法启动用户实例。  
  
> **注意：**用户实例是一项功能的[!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)]仅。  
  
> **请注意**调用从[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]或[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]，使用名称**sys.dm_pdw_nodes_os_child_instances**。  
  
|列|数据类型|Description|  
|------------|---------------|-----------------|  
|**owning_principal_name**|**nvarchar(256)**|为其创建该用户实例的用户的名称。|  
|owning_principal_sid|nvarchar(256)|拥有该用户实例的主体的 SID（安全标识符）。 它与 Windows SID 相匹配。|  
|owning_principal_sid_binary|varbinary(85)|拥有用户实例的用户的二进制版 SID。|  
|**实例名称**|**nvarchar （128)**|该用户实例的名称。|  
|**instance_pipe_name**|**nvarchar(260)**|创建用户实例时，便会创建与应用程序连接的命名管道。 可以在连接字符串中使用该名称以连接到该用户实例。|  
|**os_process_id**|**Int**|该用户实例的 Windows 进程的进程号。|  
|**os_process_creation_date**|**日期时间**|上次启动该用户实例进程的日期和时间。|  
|**heart_beat**|**nvarchar(5)**|该用户实例的当前状态，可以是 ALIVE 或 DEAD。|  
|**pdw_node_id**|**int**|**适用于**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]，[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> 此分布的节点标识符。|  
  
## <a name="permissions"></a>Permissions  
 要求具有服务器的 VIEW SERVER STATE 权限。  
  
## <a name="remarks"></a>注释  
 有关动态管理视图的详细信息，请参阅[动态管理视图和函数 &#40;Transact SQL &#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)中[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]联机丛书。  
  
## <a name="see-also"></a>另请参阅  
 [非管理员的用户实例](http://msdn.microsoft.com/en-us/85385aae-10fb-4f8b-9eeb-cce2ee7da019)  
  
  


