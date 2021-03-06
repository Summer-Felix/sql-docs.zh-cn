---
title: "sp_help_category (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/09/2016
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
- sp_help_category
- sp_help_category_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_category
ms.assetid: 8cad1dcc-b43e-43bd-bea0-cb0055c84169
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: debc3b8cef2aeb0a9f4893ff5e9287a2a5fdd016
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sphelpcategory-transact-sql"></a>sp_help_category (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  提供有关作业、警报或操作员的指定类的信息。  
   
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_help_category [ [ @class = ] 'class' ]   
     [ , [ @type = ] 'type' ]   
     [ , [ @name = ] 'name' ]   
     [ , [ @suffix = ] suffix ]   
```  
  
## <a name="arguments"></a>参数  
 [ **@class=**] **'***class***'**  
 请求其信息的类。 *类*是**varchar(8)**，默认值为**作业**。 *类*可以是下列值之一。  
  
|“值”|Description|  
|-----------|-----------------|  
|**JOB**|提供有关作业类别的信息。|  
|**警报**|提供有关警报类别的信息。|  
|**运算符**|提供有关操作员类别的信息。|  
  
 [ **@type=** ] **'***type***'**  
 请求其信息的类别的类型。 *类型*是**varchar(12)**，默认值为 NULL，并且可以为这些值之一。  
  
|“值”|Description|  
|-----------|-----------------|  
|**本地**|本地作业类别。|  
|**多的服务器**|多服务器作业类别。|  
|**NONE**|以外的其他类类别**作业**。|  
  
 [ **@name=** ] **'***name***'**  
 请求其信息的类别的名称。 *名称*是**sysname**，默认值为 NULL。  
  
 [ **@suffix=** ] *suffix*  
 指定是否**category_type**结果集中的列是 ID 或名称。 *后缀*是**位**，默认值为**0**。 **1**显示**category_type**名称和**0**显示为一个 id。  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="result-sets"></a>结果集  
 当 **@suffix** 是**0**， **sp_help_category**返回以下结果集：  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|类别 ID|  
|**category_type**|**tinyint**|类别的类型：<br /><br /> **1** = Local<br /><br /> **2** = 多服务器<br /><br /> **3** = None|  
|**名称**|**sysname**|类别名称|  
  
 当 **@suffix** 是**1**， **sp_help_category**返回以下结果集：  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|类别 ID|  
|**category_type**|**sysname**|类别的类型。 之一**本地**，**多服务器**，或**NONE**|  
|**名称**|**sysname**|类别名称|  
  
## <a name="remarks"></a>注释  
 **sp_help_category**必须从运行**msdb**数据库。  
  
 如果未指定参数，则结果集将提供有关所有作业类别的信息。  
  
## <a name="permissions"></a>权限  
 默认情况下，只有 **sysadmin** 固定服务器角色的成员才可以执行此存储过程。 其他用户必须被授予 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb **数据库中下列** 代理固定数据库角色的权限之一：  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 有关这些角色的权限的详细信息，请参阅 [SQL Server 代理固定数据库角色](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79)。  
  
## <a name="examples"></a>示例  
  
### <a name="a-returning-local-job-information"></a>A. 返回本地作业信息  
 以下示例将返回有关在本地管理的作业的信息。  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_category  
    @type = N'LOCAL' ;  
GO  
```  
  
### <a name="b-returning-alert-information"></a>B. 返回警报信息  
 以下示例将返回有关 Replication 警报类别的信息。  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_category  
    @class = N'ALERT',  
    @name = N'Replication' ;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_add_category &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-category-transact-sql.md)   
 [sp_delete_category &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-category-transact-sql.md)   
 [sp_update_category &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-update-category-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
