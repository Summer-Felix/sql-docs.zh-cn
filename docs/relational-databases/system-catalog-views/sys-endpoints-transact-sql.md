---
title: "sys.endpoints (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- endpoints
- sys.endpoints
- endpoints_TSQL
- sys.endpoints_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.endpoints catalog view
ms.assetid: e6dafa4e-e47e-43ec-acfc-88c0af53c1a1
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1ded68aefc2121f651b9005fe3e75b64ec80dc0c
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sysendpoints-transact-sql"></a>sys.endpoints (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  在系统中创建的每个端点在都表中占一行。 始终只能有一个 SYSTEM 端点。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**名称**|**sysname**|终结点的名称。 是在服务器中唯一的。 不可为 null。|  
|**endpoint_id**|**int**|端点 ID。 是在服务器中唯一的。 ID 小于 65536 的端点是系统端点。 不可为 null。|  
|**principal_id**|**int**|被创建并拥有该端点的服务器主体的 ID。 可以为 Null。|  
|**协议**|**tinyint**|端点协议。<br /><br /> 1 = HTTP<br /><br /> 2 = TCP<br /><br /> 3 = Name pipes<br /><br /> 4 = Shared memory<br /><br /> 5 = Virtual Interface Adapter (VIA)<br /><br /> 不可为 null。|  
|**protocol_desc**|**nvarchar(60)**|端点协议的说明。 可以为 NULL。 可以是以下值之一：<br /><br /> **HTTP**<br /><br /> **TCP**<br /><br /> **NAMED_PIPES**<br /><br /> **SHARED_MEMORY**<br /><br /> **通过**注意： 不推荐使用通过协议。 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|  
|**type**|**tinyint**|端点负载的类型。<br /><br /> 1 = SOAP<br /><br /> 2 = TSQL<br /><br /> 3 = SERVICE_BROKER<br /><br /> 4 = DATABASE_MIRRORING<br /><br /> 不可为 null。|  
|**type_desc**|**nvarchar(60)**|端点负载类型的说明。 可以为 Null。 可以是以下值之一：<br /><br /> **SOAP**<br /><br /> **TSQL**<br /><br /> **SERVICE_BROKER**<br /><br /> **DATABASE_MIRRORING**|  
|**状态**|**tinyint**|端点的状态。<br /><br /> 0 = STARTED，侦听并处理请求。<br /><br /> 1 = STOPPED，侦听但不处理请求。<br /><br /> 2 = DISABLED，不进行侦听。<br /><br /> 默认状态为 1。 可以为 Null。|  
|**state_desc**|**nvarchar(60)**|端点状态的说明。<br /><br /> STARTED = 侦听并处理请求。<br /><br /> STOPPED = 侦听但不处理请求。<br /><br /> DISABLED = 不进行侦听。<br /><br /> 默认状态为 STOPPED。<br /><br /> 可以为 Null。|  
|**is_admin_endpoint**|**bit**|指示端点是否用于管理。<br /><br /> 0 = 非管理端点。<br /><br /> 1 = 端点为管理端点。<br /><br /> 不可为 null。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [终结点目录视图 &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql.md)   
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
