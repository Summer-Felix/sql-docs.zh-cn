---
title: "其他批注 (SQLXML 4.0) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 72a8024f46921af6b8e52222c86d89fce1c8dc7b
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="annotation-interpretation---other-annotations"></a>批注解释的其他批注
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
除本节上文的主题中介绍的批注之外，XML 大容量加载还解释了以下其他批注：  
  
 **sql:id-prefix**  
 如果架构为 XML 数据指定了前缀，XML 大容量加载在将这些数据发送到 Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之前会删除这些前缀。  
  
 **sql:use-cdata**  
 XML 大容量加载读取存储在 CDATA 部分中的文本，然后将其发送到 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
 **sql:url-encode**  
 XML 大容量加载不支持此批注。 例如，不能在 XML 数据输入中指定某一 URL 并期望大容量加载从该位置读取数据，以将其存储在数据库中。  
  
 **sql:is-mapping-schema**  
 XML 大容量加载不支持此批注，也不支持**sql:id**。  
  
> [!NOTE]  
>  XML 大容量加载不支持内联映射架构。  
  
 **sql:key-fields**  
 XML 大容量加载始终忽略此批注。  
  
## <a name="see-also"></a>另请参阅  
 [批注解释 &#40;SQLXML 4.0 &#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sqlxml-4-0.md)  
  
  
