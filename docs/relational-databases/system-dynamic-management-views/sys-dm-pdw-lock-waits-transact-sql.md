---
title: "sys.dm_pdw_lock_waits (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/07/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 8ef966f8-d14e-40d3-9626-3508ada9b8fb
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 982f09ecacbf68ab0e55c41943f765c8f8cdedc8
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sysdmpdwlockwaits-transact-sql"></a>sys.dm_pdw_lock_waits (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  保存有关等待锁的请求的信息。  
  
|列名|数据类型|Description|范围|  
|-----------------|---------------|-----------------|-----------|  
|wait_id|**bigint**|请求的等待列表中的位置。|基于 0 的序号。 这不是唯一跨所有等待条目。|  
|session_id|**nvarchar(32)**|在其中发生等待状态的会话 ID。|请参阅中的 session_id [sys.dm_pdw_exec_sessions &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-sessions-transact-sql.md).|  
|type|**nvarchar(255)**|等待此条目表示的类型。|可能的值：<br /><br /> 共享<br /><br /> SharedUpdate<br /><br /> ExclusiveUpdate<br /><br /> 排他|  
|object_type|**nvarchar(255)**|通过在等待受影响的对象类型。|可能的值：<br /><br /> OBJECT<br /><br /> DATABASE<br /><br /> SYSTEM<br /><br /> SCHEMA<br /><br /> APPLICATION|  
|object_name|**nvarchar(386)**|名称或 GUID 指定等待受影响的对象。|表和视图将显示为三个部分组成的名称。<br /><br /> 索引和统计信息将显示具有由四部分构成的名称。<br /><br /> 名称、 主体和数据库是字符串名称。|  
|request_id|**nvarchar(32)**|在其发生等待状态的请求的 ID。|请求的 ID。<br /><br /> 这是负载请求的 GUID。|  
|request_time|**datetime**|请求的锁或资源的时间。||  
|acquire_time|**datetime**|获取锁或资源的时间。||  
|state|**nvarchar(50)**|等待状态的状态。|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|priority|**int**|等待项的优先级。|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
  
## <a name="see-also"></a>另请参阅  
 [SQL 数据仓库和并行数据仓库动态管理视图 &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
