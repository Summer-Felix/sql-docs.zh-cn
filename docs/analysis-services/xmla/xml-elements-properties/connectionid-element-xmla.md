---
title: "ConnectionID 元素 (XMLA) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ConnectionID Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#ConnectionID
- http://schemas.microsoft.com/analysisservices/2003/engine#ConnectionID
- microsoft.xml.analysis.connectionid
helpviewer_keywords: ConnectionID element
ms.assetid: de044fb2-f713-46b2-8899-14e8d515e823
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a8a8ec3a265b709415fd9e1a2554513cc9a0751d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="connectionid-element-xmla"></a>ConnectionID 元素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]标识对其执行父活动连接[取消](../../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md)元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Cancel>  
   ...  
   <ConnectionID>...</ConnectionID>  
   ...  
</Cancel>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|Integer|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[取消](../../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>另请参阅  
 [CancelAssociated 元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/cancelassociated-element-xmla.md)   
 [SessionID 元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/sessionid-element-xmla.md)   
 [SPID 元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/spid-element-xmla.md)   
 [属性 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
