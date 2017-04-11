---
title: "Oracle CDC 实例数据类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
caps.latest.revision: 9
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 9
---
# Oracle CDC 实例数据类型
  Oracle CDC 实例支持大多数 Oracle 数据类型。 下面的部分介绍支持的数据类型和不支持的数据类型。  
  
## 支持的数据类型  
 下表介绍可捕获的 Oracle 数据类型及其与更改表中 SQL Server 数据类型的默认映射。 在为源 Oracle 表添加捕获实例时，您可以覆盖其中某些映射。  
  
|Oracle 数据库数据类型|SQL Server 数据类型|  
|-------------------------------|--------------------------|  
|BINARY_FLOAT|REAL|  
|BINARY_DOUBLE|FLOAT|  
|CHAR|NVARCHAR|  
|DATE|DATETIME|  
|FLOAT|FLOAT|  
|INT|NUMERIC (38)|  
|INTERVAL|DATETIME|  
|NCHAR|NVARCHAR|  
|NUMBER|FLOAT|  
|NAVARCHAR2|NVARCHAR|  
|RAW|VARBINARY|  
|REAL|FLOAT|  
|TIMESTAMP|DATETIME2|  
|TIMESTAMP WITH TIME ZONE|VARCHAR (37)|  
|TIMESTAMP WITH LOCAL TIME ZONE|VARCHAR (37)|  
|VARCHAR2|VARCHAR|  
|XMLTYPE|NVARCHAR (MAX)|  
  
## 不支持的数据类型  
 无法捕获含以下 Oracle 数据类型的列的源 Oracle 表。 具有这些数据类型的捕获列将显示为 Null；但是，其值中的更改将在捕获表的更改掩码中指示。  
  
-   LONG  
  
-   XMLTYPE  
  
-   BLOB  
  
-   CLOB  
  
 无法捕获含以下 Oracle 数据类型的列的源 Oracle 表。  
  
-   BFILE  
  
-   ROWID  
  
-   REF  
  
-   UROWID  
  
-   嵌套表  
  
 如果在表中存在以下数据类型，则它们将阻止 LogMinder 获取任何表列的任何数据：  
  
-   用户定义数据类型  
  
-   VARRAY  
  
## 另请参阅  
 [Change Data Capture Designer for Oracle by Attunity](../../integration-services/change-data-capture/change-data-capture-designer-for-oracle-by-attunity.md)   
 [Oracle CDC 实例](../../integration-services/change-data-capture/the-oracle-cdc-instance.md)  
  
  