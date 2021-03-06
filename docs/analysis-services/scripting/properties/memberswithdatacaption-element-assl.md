---
title: "MembersWithDataCaption 元素 (ASSL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: MembersWithDataCaption Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: MembersWithDataCaption
helpviewer_keywords: MembersWithDataCaption element
ms.assetid: a5d59efd-5d67-485b-a360-67d54a1fe394
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 9554591775b1b12dd56a38bd49a55bd54713c4f8
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="memberswithdatacaption-element-assl"></a>MembersWithDataCaption 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]提供用于为系统生成的数据成员创建标题的模板字符串。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<AttributeTranslation> <!-- or DimensionAttribute -->  
   ...  
   <MembersWithDataCaption>...</MembersWithDataCaption>  
   ...  
</AttributeTranslation>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|Description|  
|--------------------|-----------------|  
|数据类型和长度|String|  
|默认值|InclusionThresholdSetting|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[AttributeTranslation](../../../analysis-services/scripting/data-type/attributetranslation-data-type-assl.md)， [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md)|  
|子元素|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Remarks  
 值**MembersWithDataCaption**元素仅由父属性 (换而言之，值[用法](../../../analysis-services/scripting/properties/usage-element-dimensionattribute-assl.md)元素**DimensionAttribute**父元素设置为*父*) 来确定父属性中的数据成员的标题。 有关数据成员的详细信息，请参阅[父子层次结构中的属性](../../../analysis-services/multidimensional-models/parent-child-dimension-attributes.md)。  
  
 对应的父级的元素**MembersWithDataCaption**分析管理对象 (AMO) 对象模型中是<xref:Microsoft.AnalysisServices.AttributeTranslation>和<xref:Microsoft.AnalysisServices.DimensionAttribute>。  
  
## <a name="see-also"></a>另请参阅  
 [MembersWithData 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/memberswithdata-element-assl.md)   
 [AttributeTranslation 数据类型 &#40;ASSL &#41;](../../../analysis-services/scripting/data-type/attributetranslation-data-type-assl.md)   
 [属性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
