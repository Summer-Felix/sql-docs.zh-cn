---
title: "backupfile (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/09/2016
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
- backupfile
- backupfile_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- file backups [SQL Server], backupfile system table
- backupfile system table
ms.assetid: f1a7fc0a-f4b4-47eb-9138-eebf930dc9ac
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 84b26ca09b8cd537ed40f0af8844f3f0c7627c86
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="backupfile-transact-sql"></a>backupfile (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  数据库的每个数据文件或日志文件在表中占一行。 表中的各列说明了进行备份时的文件配置。 是否在备份中包括的文件由**is_present**列。 此表存储在**msdb**数据库。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**backup_set_id**|**int**|包含备份集的文件的唯一标识号。 引用**backupset(backup_set_id)**。|  
|**first_family_number**|**tinyint**|包含该备份文件的第一个介质的介质簇号。 可以为 NULL。|  
|**first_media_number**|**int**|包含该备份文件的第一个介质的介质号。 可以为 NULL。|  
|**filegroup_name**|**nvarchar(128)**|包含已备份数据库文件的文件组的名称。 可以为 NULL。|  
|**page_size**|**int**|页大小（字节）。|  
|**file_number**|**numeric(10,0)**|在数据库中唯一文件标识号 (对应于**sys.database_files**。**file_id**)。|  
|**backed_up_page_count**|**numeric(10,0)**|已备份的页数。 可以为 NULL。|  
|**file_type**|**char(1)**|已备份文件，可以是下列类型之一：<br /><br /> D = [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据文件。<br /><br /> L = [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 日志文件。<br /><br /> F = 全文目录。<br /><br /> 可以为 NULL。|  
|**source_file_block_size**|**numeric(10,0)**|原始数据或日志文件备份时所在的设备。 可以为 NULL。|  
|**file_size**|**numeric(20,0)**|备份文件的长度（字节）。 可以为 NULL。|  
|**logical_name**|**nvarchar(128)**|备份文件的逻辑名称。 可以为 NULL。|  
|**physical_drive**|nvarchar(260)|物理驱动器或分区名称。 可以为 NULL。|  
|**physical_name**|nvarchar(260)|物理（操作系统）文件名的剩余部分。 可以为 NULL。|  
|**状态**|**tinyint**|文件的状态，可以是下列值之一：<br /><br /> 0 = ONLINE <br /><br /> 1 = RESTORING<br /><br /> 2 = RECOVERING<br /><br /> 3 = RECOVERY PENDING <br /><br /> 4 = SUSPECT <br /><br /> 6 = OFFLINE <br /><br /> 7 = DEFUNCT<br /><br /> 8 = 删除<br /><br /> 注意： 值 5 将跳过，以便这些值对应于数据库状态的值。|  
|**state_desc**|**nvarchar(64)**|文件状态的说明，可以是下列值之一：<br /><br /> ONLINE RESTORING <br /><br /> RECOVERING<br /><br /> RECOVERY_PENDING<br /><br /> SUSPECT OFFLINE DEFUNCT|  
|**create_lsn**|**numeric(25,0)**|创建文件时的日志序列号。|  
|**drop_lsn**|**numeric(25,0)**|删除文件时的日志序列号。 可以为 NULL。<br /><br /> 如果文件尚未删除，该值为 NULL。|  
|**file_guid**|**uniqueidentifier**|文件的唯一标识符。|  
|**read_only_lsn**|**numeric(25,0)**|包含该文件的文件组从读写属性更改为只读属性（最新更改）时的日志序列号。 可以为 NULL。|  
|**read_write_lsn**|**numeric(25,0)**|包含该文件的文件组从只读属性更改为读写属性（最新更改）时的日志序列号。 可以为 NULL。|  
|**differential_base_lsn**|**numeric(25,0)**|差异备份的基准 LSN。 差异备份仅数据区具有日志序列号等于或大于包括**differential_base_lsn**。<br /><br /> 对于其他备份类型，该值为 NULL。|  
|**differential_base_guid**|**uniqueidentifier**|对于差异备份，该值为形成文件差异基准的最新数据备份的唯一标识符；如果该值为 NULL，则文件包含在差异备份中，但是在创建基准后添加的。<br /><br /> 对于其他备份类型，该值为 NULL。|  
|**backup_size**|**numeric(20,0)**|此文件的备份的大小（字节）。|  
|**filegroup_guid**|**uniqueidentifier**|文件组的 ID。 若要查找 backupfilegroup 表中的文件组信息，请使用**filegroup_guid**与**backup_set_id**。|  
|**is_readonly**|**bit**|1 = 文件为只读。|  
|**is_present**|**bit**|1 = 文件包含在备份集中。|  
  
## <a name="remarks"></a>注释  
 RESTORE VERIFYONLY 从*backup_device*与 LOADHISTORY 填充的列**backupmediaset**介质集标头中的相应值的表。  
  
 若要减少在此表，其他备份和历史记录表中的行数，执行[sp_delete_backuphistory](../../relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql.md)存储过程。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/backup-and-restore-tables-transact-sql.md)   
 [backupfilegroup (Transact-SQL)](../../relational-databases/system-tables/backupfilegroup-transact-sql.md)   
 [backupmediafamily (Transact-SQL)](../../relational-databases/system-tables/backupmediafamily-transact-sql.md)   
 [backupmediaset (Transact-SQL)](../../relational-databases/system-tables/backupmediaset-transact-sql.md)   
 [backupset (Transact-SQL)](../../relational-databases/system-tables/backupset-transact-sql.md)   
 [系统表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/system-tables-transact-sql.md)  
  
  
