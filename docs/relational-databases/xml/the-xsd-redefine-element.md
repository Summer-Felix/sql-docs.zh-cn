---
title: "&lt;xsd:redefine&gt; 元素 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3865dc2690b6d78acb0d24fc5190ab394dfc0a83
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="the-ltxsdredefinegt-element"></a>&lt;xsd:redefine&gt; 元素
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
W3C XSD **redefine** 元素为重新定义架构组件提供了支持。 但是，对此指令的支持可能会严重影响性能，同时还要求 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 重新验证与重新定义后的架构关联的 **xml** 数据类型的所有实例。 因此， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 不支持此元素。 服务器拒绝包含 **\<xsd:redefine>** 元素的 XML 架构。  
  
 若要更新架构或其组件，您可以改为执行以下操作：  
  
1.  用修改后的架构组件创建新的 XML 架构集合。  
  
2.  重新类型化使用要重新定义的 XML 架构集合的所有 **xml** 数据类型 (XML DT)，以便改用新的 XML 架构集合。 为此，请使用 ALTER TABLE 命令的 ALTER COLUMN 选项来重新类型化列，或更改对变量或参数的 XML 架构集合约束。  
  
3.  删除旧版本的 XML 架构集合。  
  
## <a name="see-also"></a>另请参阅  
 [在服务器上使用 XML 架构集合的要求和限制](../../relational-databases/xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
