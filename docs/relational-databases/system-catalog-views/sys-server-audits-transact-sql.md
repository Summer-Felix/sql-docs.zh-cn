---
title: "sys.server_audits (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 04/05/2016
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
- server_audits_TSQL
- sys.server_audits_TSQL
- sys.server_audits
- server_audits
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_audits catalog view
ms.assetid: c2c4a000-1127-46a8-b1e9-947fd1136e1e
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: afd66281887431849c7e1c1983299c6736ff878b
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sysserveraudits-transact-sql"></a>sys.server_audits (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  服务器实例中每个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 审核都各占一行。 有关详细信息，请参阅 [SQL Server Audit（数据库引擎）](../../relational-databases/security/auditing/sql-server-audit-database-engine.md)。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**audit_id**|**int**|审核的 ID。|  
|**名称**|**sysname**|审核的名称。|  
|**audit_guid**|**uniqueidentifier**|用于枚举审核的 GUID 审核与成员服务器 &#124; 在服务器启动和数据库的数据库审核规范附加操作。|  
|**create_date**|**datetime**|创建审核的 UTC 日期。|  
|**modify_date**|**datetime**|上次修改审核的 UTC 日期。|  
|**principal_id**|**int**|审核，如注册到服务器的所有者的 ID。|  
|**type**|**char(2)**|审核类型：<br /><br /> SL – NT 安全事件日志<br /><br /> AL – NT 应用程序事件日志<br /><br /> FL – 文件系统中的文件|  
|**type_desc**|**nvarchar(60)**|SECURITY LOG<br /><br /> APPICATION LOG<br /><br /> FILE|  
|**on_failure**|**tinyint**|失败时要写入的操作项：<br /><br /> 0 – 继续<br /><br /> 1 – 关闭服务器实例<br /><br /> 2 – 失败操作|  
|**on_failure_desc**|**nvarchar(60)**|失败时要写入的操作项：<br /><br /> CONTINUE<br /><br /> SHUTDOWN SERVER INSTANCE<br /><br /> FAIL_OPERATION|  
|**is_state_enabled**|**tinyint**|0 – 禁用<br /><br /> 1 - 启用|  
|**queue_delay**|**int**|写入磁盘前等待的最长时间（以毫秒为单位）。 如果为 0，审核将保证执行写入操作，事件才能继续。|  
|**谓词**|**nvarchar(3000)**|应用于事件谓词表达式。|  
  
## <a name="permissions"></a>Permissions  
 具有主体**ALTER ANY SERVER AUDIT**或**VIEW ANY DEFINITION**权限有权访问此目录视图。 此外，必须没有拒绝主体**VIEW ANY DEFINITION**权限。  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建服务器审核 &#40;Transact SQL &#41;](../../t-sql/statements/create-server-audit-transact-sql.md)   
 [ALTER SERVER AUDIT &#40;Transact SQL &#41;](../../t-sql/statements/alter-server-audit-transact-sql.md)   
 [DROP SERVER AUDIT &#40;Transact SQL &#41;](../../t-sql/statements/drop-server-audit-transact-sql.md)   
 [创建服务器审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/create-server-audit-specification-transact-sql.md)   
 [ALTER SERVER AUDIT SPECIFICATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-server-audit-specification-transact-sql.md)   
 [删除服务器审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/drop-server-audit-specification-transact-sql.md)   
 [创建数据库审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/create-database-audit-specification-transact-sql.md)   
 [ALTER DATABASE AUDIT SPECIFICATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-database-audit-specification-transact-sql.md)   
 [删除数据库审核规范 &#40;Transact SQL &#41;](../../t-sql/statements/drop-database-audit-specification-transact-sql.md)   
 [ALTER AUTHORIZATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-authorization-transact-sql.md)   
 [sys.fn_get_audit_file &#40;Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-get-audit-file-transact-sql.md)   
 [sys.server_file_audits &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-file-audits-transact-sql.md)   
 [sys.server_audit_specifications &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specifications-transact-sql.md)   
 [sys.server_audit_specification_details &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specification-details-transact-sql.md)   
 [sys.database_audit_specifications &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specifications-transact-sql.md)   
 [sys.database_audit_specification_details &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specification-details-transact-sql.md)   
 [sys.dm_server_audit_status &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-audit-status-transact-sql.md)   
 [sys.dm_audit_actions &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-audit-actions-transact-sql.md)   
 [sys.dm_audit_class_type_map &#40;Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-audit-class-type-map-transact-sql.md)   
 [创建服务器审核和服务器审核规范](../../relational-databases/security/auditing/create-a-server-audit-and-server-audit-specification.md)  
  
  
