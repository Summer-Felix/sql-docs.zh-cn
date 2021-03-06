---
title: "sp_help_jobhistory (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
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
- sp_help_jobhistory_TSQL
- sp_help_jobhistory
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_jobhistory
ms.assetid: a944d44e-411b-4735-8ce4-73888d4262d7
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: de1836ee52354e96341386db5dfd33297f2d9be6
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sphelpjobhistory-transact-sql"></a>sp_help_jobhistory (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  为多服务器管理域中的服务器提供有关作业的信息。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_help_jobhistory [ [ @job_id = ] job_id ]   
     [ , [ @job_name = ] 'job_name' ]   
     [ , [ @step_id = ] step_id ]   
     [ , [ @sql_message_id = ] sql_message_id ]   
     [ , [ @sql_severity = ] sql_severity ]   
     [ , [ @start_run_date = ] start_run_date ]   
     [ , [ @end_run_date = ] end_run_date ]   
     [ , [ @start_run_time = ] start_run_time ]   
     [ , [ @end_run_time = ] end_run_time ]   
     [ , [ @minimum_run_duration = ] minimum_run_duration ]   
     [ , [ @run_status = ] run_status ]   
     [ , [ @minimum_retries = ] minimum_retries ]   
     [ , [ @oldest_first = ] oldest_first ]   
     [ , [ @server = ] 'server' ]   
     [ , [ @mode = ] 'mode' ]  
```  
  
## <a name="arguments"></a>参数  
 [ **@job_id=** ] *job_id*  
 作业标识号。 *job_id*是**uniqueidentifier**，默认值为 NULL。  
  
 [ **@job_name=** ] **'***job_name***'**  
 作业的名称。 *job_name*是**sysname**，默认值为 NULL。  
  
 [ **@step_id=** ] *step_id*  
 步骤标识号。 *step_id*是**int**，默认值为 NULL。  
  
 [ **@sql_message_id=** ] *sql_message_id*  
 执行作业时由 Microsoft SQL Server 返回的错误消息的标识号。 *sql_message_id*是**int**，默认值为 NULL。  
  
 [ **@sql_severity=** ] *sql_severity*  
 执行作业时由 SQL Server 返回的错误消息的严重级别。 *sql_severity*是**int**，默认值为 NULL。  
  
 [ **@start_run_date=** ] *start_run_date*  
 开始作业的日期。 *start_run_date*是**int**，默认值为 NULL。 *start_run_date*必须在窗体中输入的 YYYYMMDD，其中 YYYY 是四个字符年，MM 是两个字符的月的名称，而 DD 是两个字符星期几名称。  
  
 [ **@end_run_date=** ] *end_run_date*  
 完成作业的日期。 *end_run_date*是**int**，默认值为 NULL。 *end_run_date*必须在窗体中输入的 YYYYMMDD，其中 YYYY 是四位数年份，MM 是两个字符的月的名称，而 DD 是两个字符星期几名称。  
  
 [ **@start_run_time=** ] *start_run_time*  
 开始作业的时间。 *start_run_time*是**int**，默认值为 NULL。 *start_run_time*必须在窗体中输入的 HHMMSS，其中 HH 为一天中的两个字符小时，MM 为两个字符每分钟一天，和 SS 是一天中的两个字符第二个。  
  
 [ **@end_run_time=** ] *end_run_time*  
 作业完成执行的时间。 *end_run_time*是**int**，默认值为 NULL。 *end_run_time*必须在窗体中输入的 HHMMSS，其中 HH 为一天中的两个字符小时，MM 为两个字符每分钟一天，和 SS 是一天中的两个字符第二个。  
  
 [ **@minimum_run_duration=** ] *minimum_run_duration*  
 完成作业所用的最短时间。 *minimum_run_duration*是**int**，默认值为 NULL。 *minimum_run_duration*必须在窗体中输入的 HHMMSS，其中 HH 为一天中的两个字符小时，MM 为两个字符每分钟一天，和 SS 是一天中的两个字符第二个。  
  
 [ **@run_status=** ] *run_status*  
 作业的执行状态。 *run_status*是**int**，默认值为 NULL，并且可以为这些值之一。  
  
|“值”|说明|  
|-----------|-----------------|  
|**0**|失败|  
|**1**|已成功|  
|**2**|重试（只针对步骤）|  
|**3**|已取消|  
|**4**|进行中的消息|  
|**5**|Unknown|  
  
 [ **@minimum_retries=** ] *minimum_retries*  
 作业应该重试运行的最少次数。 *minimum_retries*是**int**，默认值为 NULL。  
  
 [ **@oldest_first=** ] *oldest_first*  
 表示是否从最早的作业开始显示输出。 *oldest_first*是**int**，默认值为**0**，其中首先显示的最新作业。 **1**首先显示最早的作业。  
  
 [ **@server=** ] **'***server***'**  
 执行作业的服务器名称。 *服务器*是**nvarchar (30)**，默认值为 NULL。  
  
 [ **@mode=** ] **'***mode***'**  
 为 SQL Server 是否打印结果集中的所有列 (**完整**) 或列的摘要。 *模式*是**varchar(7)**，默认值为**摘要**。  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="result-sets"></a>结果集  
 实际的列列表取决于值*模式*。 最全面的列如下所示和时返回*模式*已满。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**instance_id**|**int**|历史记录条目标识号。|  
|**job_id**|**uniqueidentifier**|作业标识号。|  
|**job_name**|**sysname**|作业名称。|  
|**step_id**|**int**|单步标识号 (将**0**作业历史记录)。|  
|**step_name**|**sysname**|步骤名称（对于作业历史记录将为 NULL）。|  
|**sql_message_id**|**int**|对于 [!INCLUDE[tsql](../../includes/tsql-md.md)] 步骤，为运行命令时遇到的最近的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 错误号。|  
|**sql_severity**|**int**|对于 [!INCLUDE[tsql](../../includes/tsql-md.md)] 步骤，为运行命令时遇到的最高级别的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 错误严重性。|  
|message|**nvarchar(1024)**|作业或步骤历史记录消息。|  
|**run_status**|**int**|作业或步骤的结果。|  
|**run_date**|**int**|作业或步骤开始执行的日期。|  
|**run_time**|**int**|作业或步骤开始执行的时间。|  
|**run_duration**|**int**|执行作业或步骤所花费的时间，以 HHMMSS 格式表示。|  
|**operator_emailed**|**nvarchar(20)**|接收有关该作业的电子邮件的操作员（对于步骤历史记录为 NULL）。|  
|**operator_netsent**|**nvarchar(20)**|接收有关该作业的网络消息的操作员（对于步骤历史记录为 NULL）。|  
|**operator_paged**|**nvarchar(20)**|接收有关该作业的寻呼的操作员（对于步骤历史记录为 NULL）。|  
|**retries_attempted**|**int**|步骤的重试次数（对于作业历史记录始终为 0）。|  
|服务器|**nvarchar(30)**|执行步骤或作业的服务器。 始终 (**本地**)。|  
  
## <a name="remarks"></a>注释  
 **sp_help_jobhistory**返回具有指定的计划作业的历史记录的报表。 如果没有指定参数，则该报表包含所有预定作业的历史记录。  
  
## <a name="permissions"></a>权限  
 默认情况下，只有 **sysadmin** 固定服务器角色的成员才可以执行此存储过程。 其他用户必须被授予 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb **数据库中下列** 代理固定数据库角色的权限之一：  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 有关这些角色的权限的详细信息，请参阅 [SQL Server 代理固定数据库角色](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79)。  
  
 成员**SQLAgentUserRole**数据库角色仅查看他们所拥有的作业的历史记录。  
  
## <a name="examples"></a>示例  
  
### <a name="a-listing-all-job-information-for-a-job"></a>A. 列出指定作业的所有作业信息  
 以下示例列出了 `NightlyBackups` 作业的所有作业信息。  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobhistory   
    @job_name = N'NightlyBackups' ;  
GO  
```  
  
### <a name="b-listing-information-for-jobs-that-match-certain-conditions"></a>B. 列出符合某些条件的作业的信息  
 以下示例针对遇到错误号为 `50100`（用户定义错误消息）、严重级别为 `20` 的错误的任何失败作业和失败作业步骤，打印所有列和所有作业的信息。  
  
```  
USE msdb  
GO  
  
EXEC dbo.sp_help_jobhistory  
    @sql_message_id = 50100,  
    @sql_severity = 20,  
    @run_status = 0,  
    @mode = N'FULL' ;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_purge_jobhistory (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
