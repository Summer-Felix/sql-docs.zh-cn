---
title: "SynchronizeSecurity 元素 (XMLA) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- SynchronizeSecurity Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.synchronizesecurity
- http://schemas.microsoft.com/analysisservices/2003/engine#SynchronizeSecurity
- urn:schemas-microsoft-com:xml-analysis#SynchronizeSecurity
helpviewer_keywords:
- SynchronizeSecurity element
ms.assetid: d37dbb95-f4a4-44ac-8eb9-f661d5bb5018
caps.latest.revision: 12
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 94f58bf16e0127b1686e83a0e81ba754c3cf0066
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="synchronizesecurity-element-xmla"></a>SynchronizeSecurity 元素 (XMLA)
  指定如何将安全定义，如角色和权限，同步期间[同步](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)命令。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Synchronize>  
   ...  
   <SynchronizeSecurity>...</SynchronizeSecurity>  
   ...  
</Synchronize>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|*SkipMembership*|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[同步](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)|  
|子元素|无|  
  
## <a name="remarks"></a>注释  
 **安全**元素确定的安全定义，如角色和权限，是否定义上[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]数据库同步期间**同步**命令。 此元素还确定是否的一部分包括的 Windows 用户帐户和组定义为安全定义的成员**同步**命令。  
  
 此元素的值限定为下表中列出的字符串之一。  
  
|值|Description|  
|-----------|-----------------|  
|*SkipMembership*|包含安全定义，但排除成员身份信息期间**同步**命令。|  
|*CopyAll*|包含安全定义和成员身份信息期间**同步**命令。|  
|*IgnoreSecurity*|排除期间安全定义**同步**命令。|  
  
## <a name="see-also"></a>另请参阅  
 [安全元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/security-element-xmla.md)   
 [属性 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  