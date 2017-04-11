---
title: "PATH 模式中的命名空间支持 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-xml"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PATH FOR XML 模式, 命名空间支持"
  - "命名空间 [SQL Server 中的 XML]"
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
caps.latest.revision: 11
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 11
---
# PATH 模式中的命名空间支持
  PATH 模式中的命名空间支持是通过使用 WITH NAMESPACES 提供的。 例如，下面的查询演示了如何使用 WITH NAMESPACES 语法声明一个命名空间 (a:)，随后即可在后续的 SELECT 语句中使用此命名空间：  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## 示例  
 以下这些示例演示了使用 PATH 模式从 SELECT 查询生成 XML 的过程。 这些查询中有许多都是针对 ProductModel 表的 Instructions 列中存储的自行车生产说明 XML 文档指定的。  
  
## 另请参阅  
 [将 PATH 模式与 FOR XML 一起使用](../../relational-databases/xml/use-path-mode-with-for-xml.md)  
  
  