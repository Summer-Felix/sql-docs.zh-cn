---
title: "其他非 SQL Server 订阅服务器 | Microsoft Docs"
ms.custom: ""
ms.date: "03/08/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "非 SQL Server 订阅服务器, 其他类型"
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
caps.latest.revision: 31
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 31
---
# 其他非 SQL Server 订阅服务器
  有关列表的非[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 订阅服务器支持的 [!INCLUDE[msCoName](../../../includes/msconame-md.md)], ，请参阅 [非 SQL Server 订阅服务器](../../../relational-databases/replication/non-sql/non-sql-server-subscribers.md)。 本主题包含有关 ODBC 驱动程序和 OLE DB 访问接口要求的信息。  
  
## ODBC 驱动程序要求  
 ODBC 驱动程序：  
  
-   必须符合一级 ODBC (ODBC level-1)。  
  
-   必须是线程安全型分发服务器环境。  
  
-   必须有事务能力。  
  
-   必须支持数据定义语言 (DDL)。  
  
-   不能为只读。  
  
-   必须支持长表名，如 **MSreplication_subscriptions**。  
  
## 使用 OLE DB 接口进行复制  
 OLE DB 访问接口必须为事务复制支持下列对象：  
  
-   **DataSource** 对象  
  
-   **Session** 对象  
  
-   **Command** 对象  
  
-   **Rowset** 对象  
  
-   **Error** 对象  
  
### DataSource 对象接口  
 为了连接到数据源，需要下列接口：  
  
-   **IDBInitialize**  
  
-   **IDBCreateSession**  
  
-   **IDBProperties**  
  
 如果访问接口支持 **IDBInfo** 接口，则 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 使用该接口检索信息（如引用的标识符字符、最大 SQL 语句长度，以及表名和列名中最大字符数）。  
  
### 会话对象接口  
 下列接口是必需的：  
  
-   **IDBCreateCommand**  
  
-   **ITransaction**  
  
-   **ITransactionLocal**  
  
-   **IDBSchemaRowset**  
  
### Command 对象接口  
 下列接口是必需的：  
  
-   **ICommand**  
  
-   **ICommandProperties**  
  
-   **ICommandText**  
  
-   **ICommandPrepare**  
  
-   **IColumnsInfo**  
  
-   **IAccessor**  
  
-   **ICommandWithParameters**  
  
 **IAccessor** 是创建参数访问器所必需的。 如果访问接口支持 **IColumnRowset**，则 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 使用该接口确定某列是否为标识列。  
  
### Rowset 对象接口  
 下列接口是必需的：  
  
-   **IRowset**  
  
-   **IAccessor**  
  
-   **IColumnsInfo**  
  
 应用程序应打开在订阅数据库中创建的已复制表上的行集。 访问行集中的数据需要**IColumnsInfo** 和 **IAccessor** 。  
  
### Error 对象接口  
 下列接口用于管理错误：  
  
-   **IErrorRecords**  
  
-   **IErrorInfo**  
  
 如果 OLE DB 访问接口支持 **ISQLErrorInfo** ，则使用它。  
  
 有关 OLE DB 访问接口的详细信息，请参阅 OLE DB 访问接口附带的文档。  
  
## 另请参阅  
 [非 SQL Server 订阅服务器](../../../relational-databases/replication/non-sql/non-sql-server-subscribers.md)  
  
  