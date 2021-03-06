---
title: sys.sp_xtp_control_query_exec_stats (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 10/13/2015
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.sp_xtp_control_query_exec_stats_TSQL
- sys.sp_xtp_control_query_exec_stats
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_xtp_control_query_exec_stats
ms.assetid: 4838125d-ad1e-479e-b7d2-42655e8f4f02
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 86ab826d23f50868259edc5ae3b2bffa55359ce2
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sysspxtpcontrolqueryexecstats-transact-sql"></a>sys.sp_xtp_control_query_exec_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  对实例的所有本机编译存储过程或特定的本机编译存储过程启用按查询的统计信息收集。  
  
 启用统计信息收集时性能下降。 如果只需要对一个或几个本机编译存储过程进行故障排除，则可仅对这些本机编译存储过程启用统计信息收集。  
  
 若要启用在过程级别的所有本机编译的存储过程的统计信息收集，请参阅[sys.sp_xtp_control_proc_exec_stats &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql.md).  
  
## <a name="syntax"></a>语法  
  
```  
sp_xtp_control_query_exec_stats [ [ @new_collection_value = ] collection_value ],  
[ [ @database_id = ] database_id   
[ , [ @xtp_object_id = ] procedure_id ] ,   
[ @old_collection_value] ]  
```  
  
## <a name="arguments"></a>参数  
 @new_collection_value = *value*  
 决定打开 (1) 还是关闭 (0) 过程级统计信息收集。  
  
 @new_collection_value设置为零在[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]启动。  
  
 @database_id= = *database_id*， @xtp_object_id = *procedure_id*  
 本机编译存储过程的数据库 ID 和对象 ID。 如果为实例启用了统计信息收集 ([sys.sp_xtp_control_proc_exec_stats &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql.md))，都会收集统计信息对本机编译存储过程。 对实例关闭统计信息收集不会关闭对个别本机编译存储过程的统计信息收集。  
  
 使用[sys.databases &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)， [sys.procedures &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-procedures-transact-sql.md)， [DB_ID &#40;Transact SQL &#41;](../../t-sql/functions/db-id-transact-sql.md)，或[OBJECT_ID &#40;Transact SQL &#41;](../../t-sql/functions/object-id-transact-sql.md)若要获取数据库和存储的过程的 Id。  
  
 @old_collection_value = *value*  
 返回当前状态。  
  
## <a name="return-code"></a>返回代码  
 0 表示成功。 非零表示失败。  
  
## <a name="permissions"></a>权限  
 要求用户为固定 sysadmin 角色的成员。  
  
## <a name="code-sample"></a>代码示例  
 以下代码示例展示如何对实例的所有本机编译存储过程启用统计信息收集，然后对特定的本机编译存储过程启用统计信息收集。  
  
```sql   
DECLARE @c bit  
  
EXEC [sys].[sp_xtp_control_query_exec_stats] @new_collection_value = 1;  
  
EXEC sp_xtp_control_query_exec_stats @old_collection_value=@c output;  
SELECT @c AS 'collection status';  
  
EXEC [sys].[sp_xtp_control_query_exec_stats] @new_collection_value = 1,   
@database_id = 5, @xtp_object_id = 341576255;  
  
EXEC sp_xtp_control_query_exec_stats @database_id = 5,   
@xtp_object_id = 341576255, @old_collection_value=@c output;  
  
SELECT @c AS 'collection status';  
```  
  
## <a name="see-also"></a>另请参阅  
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [内存中 OLTP（内存中优化）](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
