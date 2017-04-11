---
title: "启用了外部脚本的服务器配置选项 | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/15/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "external scripts enabled"
  - "external_scripts_enabled_TSQL"
helpviewer_keywords: 
  - "启用了外部脚本的选项"
ms.assetid: 9d0ce165-8719-4007-9ae8-00f85cab3a0d
caps.latest.revision: 9
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 8
---
# 启用了外部脚本的服务器配置选项
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  使用 **external scripts enabled** 选项启用包含某些远程语言扩展的脚本执行。 默认情况下，此属性将为“OFF”。 如果安装了“高级分析服务”  ，安装程序可以根据需要将此属性设置为 true。  
  
||  
|-|  
|**适用范围**：[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]（[!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 到 [当前版本](http://go.microsoft.com/fwlink/p/?LinkId=299658)）。|  
  
 在使用 **sp_execute_external_script** 过程执行外部脚本之前，必须启用“已启用外部脚本”选项。 使用 **sp_execute_external_script** 执行受支持的语言（如 R）编写的脚本。在 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 中，[!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)] 由与 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] 一起安装的服务器组件工作站工具集和将数据科学家与 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 高性能环境相连的连接库构成。  在 **安装程序安装期间安装** 高级分析扩展 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 功能，以启用 R 脚本的执行。 有关详细信息，请参阅 [Installing Previous Versions of SQL Server R Services](../Topic/Installing%20Previous%20Versions%20of%20SQL%20Server%20R%20Services.md)。  
  
 执行下面的脚本，以启用外部脚本。  
  
```  
sp_configure 'external scripts enabled', 1;  
RECONFIGURE;  
```  
  
 你必须重启 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 以使此更改生效。  
  
## 另请参阅  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE (Transact-SQL)](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [sp_execute_external_script (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md)   
 [SQL Server R Services](../../advanced-analytics/r-services/sql-server-r-services.md)  
  
  