---
title: "sys.dm_exec_compute_node_status (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DM_EXEC_COMPUTE_NODE_STATUS_TSQL
- DM_EXEC_COMPUTE_NODE_STATUS
dev_langs:
- TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- dm_exec_compute_node_status
- sys.dm_exec_compute_node_status management view
ms.assetid: b606f91f-3a08-4a4f-bb57-32ae155b3738
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f898f754f0b39b0f5746d8ed076c75d26354bccd
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sysdmexeccomputenodestatus-transact-sql"></a>sys.dm_exec_compute_node_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  保存有关的性能和状态的所有 PolyBase 节点的其他信息。 列出每个节点的一行。  
  
|列名|数据类型|Description|范围|  
|-----------------|---------------|-----------------|-----------|  
|compute_node_id|**int**|与节点关联的唯一数字 id。|不管哪种类型的横向扩展群集之间唯一。|  
|process_id|**int**|||  
|process_name|**nvarchar(255)**|节点的逻辑名称。|相应的长度的任何字符串。|  
|allocated_memory|**bigint**|分配此节点上的内存的总数。||  
|available_memory|**bigint**|在此节点上的总可用内存。||  
|process_cpu_usage|**bigint**|总进程 CPU 使用率，以刻度为单位。||  
|total_cpu_usage|**bigint**|总 CPU 使用率，以刻度为单位。||  
|thread_count|**bigint**|在此节点上使用的线程的总数。||  
|handle_count|**bigint**|使用此节点上的句柄的总数。||  
|total_elapsed_time|**bigint**|系统启动或重新启动后经过的总时间。|系统启动或重新启动后经过的总时间。 如果 total_elapsed_time 超过一个整数 （以毫秒为单位的 24.8 天） 的最大值，它将导致具体化失败由于溢出。以毫秒为单位的最大值相当于 24.8 天。|  
|is_available|**bit**|指示此节点是否可用的标志。||  
|sent_time|**datetime**|此发送网络包的最后一个时间||  
|received_time|**datetime**|最后一次此节点发送网络包。||  
|error_id|**nvarchar(36)**|此节点发生的最后一个错误的唯一标识符。||  
  
## <a name="see-also"></a>另请参阅  
 [PolyBase 使用动态管理视图进行故障排除](http://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [动态管理视图和函数 (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [与数据库相关的动态管理视图 &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  
