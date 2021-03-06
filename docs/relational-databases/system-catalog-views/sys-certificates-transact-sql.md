---
title: "sys.certificates (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- certificates
- certificates_TSQL
- sys.certificates_TSQL
- sys.certificates
dev_langs:
- TSQL
helpviewer_keywords:
- sys.certificates catalog view
ms.assetid: e5046102-a65c-401e-b80d-05636884dec9
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 60cb7a204aaa38a3aaaa24b8c04bb676715de783
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="syscertificates-transact-sql"></a>sys.certificates (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  为数据库中的每个证书返回一行。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**名称**|**sysname**|证书的名称。 在该数据库中是唯一的。|  
|**certificate_id**|**int**|证书的 ID。 在该数据库中是唯一的。|  
|**principal_id**|**int**|拥有此证书的数据库主体的 ID。|  
|**pvt_key_encryption_type**|**char(2)**|私钥加密方式。<br /><br /> NA = 证书没有私钥<br /><br /> MK = 使用主密钥加密私钥<br /><br /> PW = 使用用户定义的密码加密私钥<br /><br /> SK = 使用服务主密钥加密私钥。|  
|**pvt_key_encryption_type_desc**|**nvarchar(60)**|对私钥加密方式的说明。<br /><br /> NO_PRIVATE_KEY<br /><br /> ENCRYPTED_BY_MASTER_KEY<br /><br /> ENCRYPTED_BY_PASSWORD<br /><br /> ENCRYPTED_BY_SERVICE_MASTER_KEY|  
|**is_active_for_begin_dialog**|**bit**|如果为 1，则证书用于启动加密的服务对话。|  
|**issuer_name**|**nvarchar(442)**|证书颁发者的名称。|  
|**cert_serial_number**|**nvarchar(64)**|证书的序列号。|  
|**sid**|**varbinary(85)**|此证书的登录 SID。|  
|**string_sid**|**nvarchar （128)**|此证书的登录 SID 的字符串表示形式。|  
|**主题**|**nvarchar(4000)**|此证书的主题。|  
|**expiry_date**|**datetime**|证书的过期时间。|  
|**start_date**|**datetime**|证书生效的时间。|  
|**指纹**|**varbinary(32)**|证书的 SHA-1 哈希。 SHA-1 哈希在全局内唯一。|  
|**attested_by**|**nvarchar(260)**|仅供系统使用。|  
|pvt_key_last_backup_date|**datetime**|上一次导出证书的私钥的日期和时间。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [安全性目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [加密层次结构](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [CREATE CERTIFICATE (Transact-SQL)](../../t-sql/statements/create-certificate-transact-sql.md)  
  
  
