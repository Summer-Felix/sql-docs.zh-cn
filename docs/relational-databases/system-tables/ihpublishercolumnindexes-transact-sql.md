---
title: "IHpublishercolumnindexes (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- IHpublishercolumnindexes
- IHpublishercolumnindexes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- IHpublishercolumnindexes system table
ms.assetid: 95b95a1d-b502-4838-825f-82a456487e25
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 21370e81d1be10aef58a5dda779f765417fc0a54
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihpublishercolumnindexes-transact-sql"></a>IHpublishercolumnindexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **IHpublishercolumnindexes**系统表映射列中的非 SQL Server 发布[IHpublishercolumns](../../relational-databases/system-tables/ihpublishercolumns-transact-sql.md)到中的索引的系统表[IHpublisherindexes](../../relational-databases/system-tables/ihpublisherindexes-transact-sql.md)系统表。 此表存储在分发数据库中。  
  
## <a name="definition"></a>定义  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**publishercolumn_id**|**int**|标识从列[IHpublishercolumns](../../relational-databases/system-tables/ihpublishercolumns-transact-sql.md)具有关联的索引。|  
|**publisherindex_id**|**int**|标识从索引[IHpublisherindexes](../../relational-databases/system-tables/ihpublisherindexes-transact-sql.md)与该列关联的表。|  
|**indid**|**int**|指示列在已发布表中的位置。|  
  
## <a name="see-also"></a>另请参阅  
 [异类数据库复制](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [复制表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
