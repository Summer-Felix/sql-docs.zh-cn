---
title: "MSrepl_originators (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- MSrepl_originators_TSQL
- MSrepl_originators
dev_langs: TSQL
helpviewer_keywords: MSrepl_originators system table
ms.assetid: a3ac20a6-73f6-4fdc-ad5f-5f72746c9871
caps.latest.revision: "26"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7fca669ba119dba475b39d41b657815a854836d4
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="msreploriginators-transact-sql"></a>MSrepl_originators (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSrepl_originators**表包含用于显示事务产生的每个可更新订阅服务器的一个行。 此表存储在分发数据库中。  
  
|列名|数据类型|说明|  
|-----------------|---------------|-----------------|  
|**id**|**int**|标识正在更新的订阅服务器。|  
|**publisher_database_id**|**int**|标识发布数据库。|  
|**srvname**|**sysname**|正在更新的服务器的名称。|  
|**dbname**|**sysname**|正在更新的数据库的名称。|  
|**publication_id**|**int**|标识发布。|  
|**dbversion**|**int**|标识数据库的版本。|  
  
## <a name="see-also"></a>另请参阅  
 [复制表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  