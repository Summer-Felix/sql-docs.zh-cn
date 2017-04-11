---
title: "创建 CLR 函数 | Microsoft Docs"
ms.custom: ""
ms.date: "03/16/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-udf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR 函数 [SQL Server]"
  - "用户定义函数 [SQL Server], CLR"
ms.assetid: a82df075-2243-4e19-bfe1-ae6d65dabd0f
caps.latest.revision: 34
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 34
---
# 创建 CLR 函数
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  可以在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中创建可在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 公共语言运行时 (CLR) 中创建的程序集中进行编程的数据库对象。 可以充分利用公共语言运行时所提供的丰富的编程模式的数据库对象包括聚合函数、函数、存储过程、触发器以及类型。  
  
 在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中创建 CLR 函数分为下列几个步骤：  
  
-   使用 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 支持的语言将函数定义为类的静态方法。 有关如何在公共语言运行时中对函数进行编程的详细信息，请参阅 [CLR 用户定义函数](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)。 然后，使用适当的语言编译器编译该类，在 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 中生成程序集。  
  
-   使用 CREATE ASSEMBLY 语句在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中注册程序集。 有关 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中的程序集的详细信息，请参阅[程序集（数据库引擎）](../../relational-databases/clr-integration/assemblies-database-engine.md)。  
  
-   通过使用 [CREATE FUNCTION](../../t-sql/statements/create-function-transact-sql.md) 语句创建引用注册程序集的函数。  
  
> [!NOTE]  
>  在 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 中部署 SQL Server 项目将在为该项目指定的数据库中注册程序集。 部署项目时，还会在数据库中为使用 **SqlFunction** 属性注释的所有方法创建 CLR 函数。 有关详细信息，请参阅 [Deploying CLR Database Objects](../../relational-databases/clr-integration/deploying-clr-database-objects.md)。  
  
> [!NOTE]  
>  默认情况下，关闭 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 执行 CLR 代码的功能。 你可以创建、更改和删除引用托管代码模块的数据库对象，但是除非通过使用 [sp_configure (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) 启用了 [clr enabled 选项](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md)，否则这些引用将不会在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中执行。  
  
## 访问外部资源  
 可以使用 CLR 函数访问外部资源，例如文件、网络资源、Web 服务及其他数据库（包括 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 远程实例）。 这可以通过使用 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 中的各种类（例如 `System.IO`、`System.WebServices` 及 `System.Sql` 等）来实现。 至少应将包含此类函数的程序集配置为设置了 EXTERNAL_ACCESS 权限，才能实现此目的。 有关详细信息，请参阅 [CREATE ASSEMBLY (Transact-SQL)](../../t-sql/statements/create-assembly-transact-sql.md)。 可以使用 SQL 客户端托管访问接口访问 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 远程实例。 但在 CLR 函数中不支持与发起服务器的环回连接。  
  
 **创建、修改或删除 SQL Server 中的程序集**  
  
-   [CREATE ASSEMBLY (Transact-SQL)](../../t-sql/statements/create-assembly-transact-sql.md)  
  
-   [ALTER ASSEMBLY (Transact-SQL)](../../t-sql/statements/alter-assembly-transact-sql.md)  
  
-   [DROP ASSEMBLY (Transact-SQL)](../../t-sql/statements/drop-assembly-transact-sql.md)  
  
 **创建 CLR 函数**  
  
-   [CREATE FUNCTION (Transact-SQL)](../../t-sql/statements/create-function-transact-sql.md)  
  
## 访问本机代码  
 通过使用托管代码中的 PInvoke，可以使用 CLR 函数来访问本机（非托管）代码，如用 C 或 C++ 编写的代码（有关详细信息，请参阅[从托管代码调用本机函数](http://go.microsoft.com/fwlink/?LinkID=181929)）。 这样，您就可以重新将旧代码用作 CLR UDF，或在本机代码中使用性能关键的 UDF。 这要求使用 UNSAFE（非安全）程序集。 有关使用 UNSAFE 程序集的注意事项，请参阅 [CLR Integration Code Access Security](../../relational-databases/clr-integration/security/clr-integration-code-access-security.md) 。  
  
## 另请参阅  
 [创建用户定义函数（数据库引擎）](../../relational-databases/user-defined-functions/create-user-defined-functions-database-engine.md)   
 [创建用户定义聚合](../../relational-databases/user-defined-functions/create-user-defined-aggregates.md)   
 [执行用户定义函数](../../relational-databases/user-defined-functions/execute-user-defined-functions.md)   
 [查看用户定义函数](../../relational-databases/user-defined-functions/view-user-defined-functions.md)   
 [公共语言运行时 (CLR) 集成编程概念](../../relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  