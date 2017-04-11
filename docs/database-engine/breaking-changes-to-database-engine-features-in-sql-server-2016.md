---
title: "SQL Server 2016 中数据库引擎功能的重大更改 | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "11/15/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "数据库引擎 [SQL Server], 新增功能"
  - "重大更改 [SQL Server]"
ms.assetid: 47edefbd-a09b-4087-937a-453cd5c6e061
caps.latest.revision: 144
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 144
---
# SQL Server 2016 中数据库引擎功能的重大更改
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  本主题介绍了 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)][!INCLUDE[ssDE](../includes/ssde-md.md)] 和 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 早期版本中的重大更改。 这些更改可能导致基于 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]的早期版本的应用程序、脚本或功能无法继续使用。 在进行升级时可能会遇到这些问题。  
  
##  <a name="a-namesql15a-breaking-changes-in-includesssql15tokensssql15mdmd"></a><a name="SQL15"></a> [!INCLUDE[ssSQL15](../includes/sssql15-md.md)] 中的重大更改  
  
-   sys.dm_io_virtual_file_stats 的 sample_ms 列已从 **int** 扩展到 **bigint** 数据类型。  
  
-   sys.fn_virtualfilestats 的 TimeStamp 列已从 **int** 扩展到 **bigint** 数据类型。  

-   使用 MD2、MD4、MD5、SHA 或 SHA1 哈希算法（不推荐）需要将数据库兼容级别设置为早于 130。  

-   在数据库兼容级别 130 以下，通过考虑导致不同转换值的毫秒小数部分，从 **datetime** 到 **datetime2** 数据类型的隐式转换显得更加准确。 只要 datetime 和 datetime2 数据类型之间存在混合比较情况，就需要使用 datetime2 数据类型的隐式转换。

  
## <a name="previous-versions"></a>先前版本  
  
-   [SQL Server 2014 中数据库引擎功能的重大更改](https://msdn.microsoft.com/library/ms143179\(v=sql.120\))  
  
-   [SQL Server 2012 中数据库引擎功能的重大更改](https://msdn.microsoft.com/library/ms143179\(v=sql.110\))  
  
-   [SQL Server 2008 中数据库引擎功能的重大更改](https://msdn.microsoft.com/library/ms143179\(v=sql.100\))  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 2016 中不推荐使用的数据库引擎功能](../database-engine/deprecated-database-engine-features-in-sql-server-2016.md)   
 [SQL Server 2016 中废止的数据库引擎功能](../database-engine/discontinued-database-engine-functionality-in-sql-server-2016.md)   
 [SQL Server 数据库引擎的向后兼容性](../database-engine/sql-server-database-engine-backward-compatibility.md)   
 [ALTER DATABASE 兼容级别 (Transact-SQL)](../Topic/ALTER%20DATABASE%20Compatibility%20Level%20\(Transact-SQL\).md)  
  
  