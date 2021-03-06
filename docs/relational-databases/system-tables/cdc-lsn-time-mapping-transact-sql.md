---
title: "cdc.lsn_time_mapping (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cdc.lsn_time_mapping
- cdc.lsn_time_mapping_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- cdc.lsn_time_mapping
ms.assetid: 1cb7aedc-48a4-486e-9b91-d30c4bd4084e
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1791e206d6b249e29068730ff36b754996e9d0e9
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cdclsntimemapping-transact-sql"></a>cdc.lsn_time_mapping (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  为每个在更改表中存在行的事务返回一行。 该表用于在日志序列号 (LSN) 提交值和提交事务的时间之间建立映射。 没有对应的更改表项的项也可以记录下来， 以便表在变更活动少或者无变更活动期间将 LSN 处理的完成过程记录下来。  
  
 我们建议您不要直接查询系统表， 相反，执行[sys.fn_cdc_map_lsn_to_time &#40;Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-cdc-map-lsn-to-time-transact-sql.md)和[sys.fn_cdc_map_time_to_lsn &#40;Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-cdc-map-time-to-lsn-transact-sql.md)系统函数。  
    
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**start_lsn**|**binary(10)**|提交的事务的 LSN。|  
|**tran_begin_time**|**datetime**|与 LSN 关联的事务开始的时间。|  
|**tran_end_time**|**datetime**|事务结束的时间。|  
|**tran_id**|**varbinary(10)**|事务 ID。|  
  
## <a name="see-also"></a>另请参阅  
 [事务日志 (SQL Server)](../../relational-databases/logs/the-transaction-log-sql-server.md)   
 [cdc。 &#60; capture_instance &#62; _CT &#40;Transact SQL &#41;](../../relational-databases/system-tables/cdc-capture-instance-ct-transact-sql.md)  
  
  
