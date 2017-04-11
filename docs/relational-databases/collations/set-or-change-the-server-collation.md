---
title: "设置或更改服务器排序规则 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "服务器排序规则 [SQL Server]"
  - "排序规则 [SQL Server], 服务器"
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
caps.latest.revision: 34
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 34
---
# 设置或更改服务器排序规则
  服务器排序规则用作与 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]的实例一起安装的所有系统数据库以及任何新创建的用户数据库的默认排序规则。 服务器排序规则是在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装期间指定的。 有关详细信息，请参阅 [Collation and Unicode Support](../../relational-databases/collations/collation-and-unicode-support.md)。  
  
## 更改服务器排序规则  
 更改 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的默认排序规则的操作可能会比较复杂，包括以下步骤：  
  
-   确保具有重新创建用户数据库及这些数据库中的所有对象所需的全部信息或脚本。  
  
-   使用工具（例如 [bcp Utility](../../tools/bcp-utility.md)）导出所有数据。 有关详细信息，请参阅[批量导入和导出数据 (SQL Server)](../../relational-databases/import-export/bulk-import-and-export-of-data-sql-server.md)。  
  
-   删除所有用户数据库。  
  
-   重新生成在 **setup** 命令的 SQLCOLLATION 属性中指定新的排序规则的 master 数据库。 例如：  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     有关详细信息，请参阅[重新生成系统数据库](../../relational-databases/databases/rebuild-system-databases.md)。  
  
-   创建所有数据库及这些数据库中的所有对象。  
  
-   导入所有数据。  
  
> [!NOTE]  
>  可以为创建的每个新数据库指定默认排序规则，而不更改 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的默认排序规则。  
  
## 另请参阅  
 [排序规则和 Unicode 支持](../../relational-databases/collations/collation-and-unicode-support.md)   
 [设置或更改数据库排序规则](../../relational-databases/collations/set-or-change-the-database-collation.md)   
 [设置或更改列排序规则](../../relational-databases/collations/set-or-change-the-column-collation.md)   
 [重新生成系统数据库](../../relational-databases/databases/rebuild-system-databases.md)  
  
  