---
title: "命名空间的 uri-从的 QName (XQuery) |Microsoft 文档"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: xquery
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- fn:namespace-uri-from-QName function
- namespace-uri-from-QName function
ms.assetid: 4ab3f003-2a3b-4268-9e88-b615e35701b2
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 94b19762329355d7e62e13fe7e8614755f3a96ce
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="functions-related-to-qnames---namespace-uri-from-qname"></a>与 QNames-命名空间 uri 从 QName 相关函数
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  返回一个字符串，表示由指定的 QName 的命名空间 uri *$arg*。 如果结果为空序列*$arg*是空的序列。  
  
## <a name="syntax"></a>语法  
  
```  
namespace-uri-from-QName($arg as xs:QName?) as xs:string?  
```  
  
## <a name="arguments"></a>参数  
 *$arg*  
 是返回其命名空间 URI 的 QName。  
  
## <a name="examples"></a>示例  
 本主题提供对存储在各种的 XML 实例的 XQuery 示例**xml** AdventureWorks 数据库中的类型列。  
  
### <a name="a-retrieve-the-namespace-uri-from-a-qname"></a>A. 检索 QName 的命名空间 URI  
 有关工作示例，请参阅[本地名称从 QName &#40;XQuery &#41;](../xquery/functions-related-to-qnames-local-name-from-qname.md).  
  
### <a name="implementation-limitations"></a>实现限制  
 限制如下：  
  
-   **Namespace-uri-from-QName()**函数将返回而不是 xs: anyuri xs: string 的实例。  
  
## <a name="see-also"></a>另请参阅  
 [与 QNames &#40; 相关的功能XQuery &#41;](http://msdn.microsoft.com/library/7e07eb26-f551-4b63-ab77-861684faff71)  
  
  
