---
title: "sys.pdw_table_mappings (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 1af14fe0-e562-4f48-a7f0-783f300a88ac
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 98f904d84f22b3b6daafeb34f063e6e42daaff2e
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="syspdwtablemappings-transact-sql"></a>sys.pdw_table_mappings (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  相关联的内部对象名称的用户表**object_id**。  
  
|列名|数据类型|Description|范围|  
|-----------------|---------------|-----------------|-----------|  
|physical_name|**nvarchar(36)**|表的物理名称。<br /><br /> **physical_name**和**object_id**窗体中的密钥，此视图。||  
|object_id|**int**|表对象 ID。 请参阅[sys.objects &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).<br /><br /> **physical_name**和**object_id**窗体中的密钥，此视图。||  
  
## <a name="see-also"></a>另请参阅  
 [SQL 数据仓库和并行数据仓库目录视图](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
 [sys.pdw_index_mappings &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-index-mappings-transact-sql.md)   
 [sys.pdw_database_mappings &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-database-mappings-transact-sql.md)  
  
  
