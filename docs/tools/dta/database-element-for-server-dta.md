---
title: "数据库元素 (DTA) 服务器 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: dta
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: XML
helpviewer_keywords: Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
caps.latest.revision: "16"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d5150ec15a3cdd1f218bb108b8e305eaae7f2121
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="database-element-for-server-dta"></a>服务器的数据库元素 (DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]指定要优化特定服务器上的数据库。  
  
## <a name="syntax"></a>语法  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|无。|  
|默认值|无。|  
|出现次数|对于每个 **Server** 元素需要使用一次或多次。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|--------------|  
|父元素|[服务器元素 &#40; DTA &#41;](../../tools/dta/server-element-dta.md)|  
|子元素|[数据库 &#40; DTA &#41; 的名称元素](../../tools/dta/name-element-for-database-dta.md)<br /><br /> [数据库 &#40; DTA &#41; 的架构元素](../../tools/dta/schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a>注释  
 在数据库引擎优化顾问 XML 架构中，此元素的名称为 **DatabaseDetailsTypecomplexType** 。 请不要将此 **Database** 元素与根级父元素为 **Configuration** 元素的元素相混淆。 有关详细信息，请参阅[用于配置的数据库元素 (DTA)](../../tools/dta/database-element-for-configuration-dta.md)。  
  
## <a name="example"></a>示例  
 有关 **Database** 元素的用法示例，请参阅 [服务器元素 (DTA)](../../tools/dta/server-element-dta.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XML 输入文件引用（数据库引擎优化顾问）](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
