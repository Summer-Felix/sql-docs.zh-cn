---
title: "FeatureSet 元素 (DTA) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "XML"
helpviewer_keywords: 
  - "FeatureSet 元素"
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
caps.latest.revision: 14
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 14
---
# FeatureSet 元素 (DTA)
  包含数据库引擎优化顾问在分析中使用的物理设计结构（索引或索引视图）。  
  
## 语法  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## 元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|**数据类型和长度**|**string**，无最大长度。|  
|**允许的值**|**IDX_IV**<br /> 索引和索引视图。<br /><br /> **IDX**<br /> 仅限索引。<br /><br /> **IV**<br /> 仅限索引视图。<br /><br /> **NCL_IDX**<br /> 仅限非聚集索引。<br /><br /> 将这些值中的一个值用于此元素。|  
|**默认值**|**IDX**|  
|**出现次数**|除非使用了 **TuningOptions** 元素，否则对每个 **DropOnlyMode** 元素仅需要一次。 如果使用 **DropOnlyMode** ，则无法使用 **FeatureSet**。 这两种元素是互相排斥的。|  
  
## 元素关系  
  
|关系|元素|  
|------------------|--------------|  
|**父元素**|[TuningOptions 元素 (DTA)](../../tools/dta/tuningoptions-element-dta.md)|  
|**子元素**|无。|  
  
## 示例  
 有关此元素的使用示例，请参阅[简单 XML 输入文件示例 (DTA)](../../tools/dta/simple-xml-input-file-sample-dta.md)。  
  
## 另请参阅  
 [XML 输入文件引用（数据库引擎优化顾问）](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  