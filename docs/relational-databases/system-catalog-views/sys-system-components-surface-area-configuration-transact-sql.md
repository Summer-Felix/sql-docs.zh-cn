---
title: "sys.system_components_surface_area_configuration (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.system_components_surface_area_configuration_TSQL
- system_components_surface_area_configuration
- system_components_surface_area_configuration_TSQL
- sys.system_components_surface_area_configuration
dev_langs: TSQL
helpviewer_keywords: sys.system_components_surface_area_configuration catalog view
ms.assetid: d9920008-3387-4f9e-8f21-47473f2ba04f
caps.latest.revision: "16"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 24797c65aa40c1938d54fa32216d06cb0a5b6550
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="syssystemcomponentssurfaceareaconfiguration-transact-sql"></a>sys.system_components_surface_area_configuration (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  对于可通过外围应用配置器组件启用或禁用的每个可执行系统对象返回一行。 有关详细信息，请参阅 [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md)。  
  
||  
|-|  
|**适用范围**： [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] （[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 到 [当前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658)）。|  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**组件**|**sysname**|组件名称。 这将使用关键字排序规则 Latin1_General_CI_AS_KS_WS。 不能为 NULL。|  
|**database_name**|**sysname**|包含此对象的数据库。 这将使用关键字排序规则 Latin1_General_CI_AS_KS_WS。 必须是下列选项之一：<br /><br /> **master**<br /><br /> **msdb**<br /><br /> **mssqlsystemresource**|  
|**schema_name**|**sysname**|包含此对象的架构。 这将使用关键字排序规则 Latin1_General_CI_AS_KS_WS。 不能为 NULL。|  
|**object_name**|**sysname**|对象的名称。 这将使用关键字排序规则 Latin1_General_CI_AS_KS_WS。 不能为 NULL。|  
|**状态**|**tinyint**|0 = 禁用<br /><br /> 1 = 启用|  
|**type**|**char(2)**|对象类型。 可以为以下各项之一：<br /><br /> P = SQL_STORED_PROCEDURE<br /><br /> PC = CLR_STORED_PROCEDURE<br /><br /> FN = SQL_SCALAR_FUNCTION<br /><br /> FS = CLR_SCALAR_FUNCTION<br /><br /> FT = CLR_TABLE_VALUED_FUNCTION<br /><br /> IF = SQL_INLINE_TABLE_VALUED_FUNCTION<br /><br /> TF = SQL_TABLE_VALUED_FUNCTION<br /><br /> X = EXTENDED_STORED_PROCEDURE|  
|**type_desc**|**nvarchar(60)**|对于对象类型的友好名称的说明。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [安全性目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
  