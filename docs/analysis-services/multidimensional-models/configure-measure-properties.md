---
title: "配置度量值属性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/03/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "累加性 [Analysis Services]"
  - "ID 属性"
  - "ErrorConfiguration 属性"
  - "AggregateFunction 属性"
  - "DisplayFolder 属性"
  - "IgnoreUnrelatedDimensions 属性"
  - "FormatString 属性"
  - "Description 属性"
  - "半累加性"
  - "属性 [Analysis Services], 度量值组"
  - "聚合函数 [Analysis Services]"
  - "DataType 属性"
  - "ProcessingMode 属性"
  - "MeasureExpression 属性"
  - "AggregationPrefix 属性"
  - "Visible 属性"
  - "属性 [Analysis Services], 度量值"
  - "StorageLocation 属性"
  - "StorageMode 属性"
  - "格式 [Analysis Services], 度量值"
  - "Source 属性"
  - "聚合 [Analysis Services], 度量值"
  - "度量值 [Analysis Services], 属性"
  - "属性 [Analysis Services]"
  - "Name 属性"
  - "度量值 [Analysis Services], 显示格式"
  - "ProcessingPriority 属性"
  - "度量值组 [Analysis Services], 属性"
  - "Type 属性"
  - "ProactiveCaching 属性"
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
caps.latest.revision: 50
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 50
---
# 配置度量值属性
  通过使用度量值的属性，您可以定义度量值的工作方式并控制如何向用户显示度量值。  
  
 当创建或编辑多维数据集或度量值时可在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 中设置属性。 你还可以编程方式（用 MDX 或 AMO）设置它们。 有关详细信息，请参阅[在多维模型中创建度量值和度量值组](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md)、[CREATE MEMBER 语句 (MDX)](../Topic/CREATE%20MEMBER%20Statement%20\(MDX\).md) 或 [AMO OLAP 基本对象的编程](../../analysis-services/multidimensional-models/analysis-management-objects/programming-amo-olap-basic-objects.md)。  
  
## 度量值属性  
 度量值从其所属的度量值组中继承某些属性，除非这些属性在度量值级别被覆盖。 度量值属性确定度量值的聚合方式、它的数据类型、对用户的显示名称、度量值将在其中出现的显示文件夹、它的格式字符串、任何度量值表达式、基础源列和它对用户的可见性。  
  
|属性|定义|  
|--------------|----------------|  
|**AggregateFunction**|必需的。 确定度量值的聚合方式。 **Sum** 是默认聚合。 有关详细信息，请参阅针对每个函数说明的 [Use Aggregate Functions](../../analysis-services/multidimensional-models/use-aggregate-functions.md) 。|  
|**DataType**|必需的。 指定与度量值绑定的基础事实数据表中的列的数据类型。 默认情况下，此值从源列继承。|  
|**Description**|提供度量值的说明，可以在客户端应用程序中显示该说明。|  
|**DisplayFolder**|指定当用户连接到多维数据集时度量值将在其中显示的文件夹。 多维数据集有很多度量值时，可以使用显示文件夹来对度量值进行分类，从而改善用户的浏览体验。|  
|**FormatString**|通过使用度量值的 **FormatString** 属性，可以选择用于向用户显示度量值的格式。<br /><br /> 虽然 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中提供了显示格式的列表，但你仍可以指定多个该列表中没有的其他格式。 您可以指定在 Microsoft Visual Basic 中有效的任何命名格式或用户定义格式。|  
|**ID**|必需的。 显示度量值的唯一标识符 (ID)。 该属性为只读。|  
|**MeasureExpression**|指定定义度量值的值的受约束的 MDX 表达式。 表达式在聚合之前在叶级进行求值，并且允许对值设置权重。 例如，在货币转换中，销售额按汇率加权。|  
|**名称**|必需的。 指定度量值的名称。|  
|**数据源**|必需的。 指定与度量值绑定的数据源视图中的列。 请参阅[数据源和绑定（SSAS 多维）](../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md)。|  
|**Visible**|确定客户端应用程序中度量值的可见性。|  
  
## 另请参阅  
 [配置度量值组属性](../../analysis-services/multidimensional-models/configure-measure-group-properties.md)   
 [修改度量值](../../analysis-services/modifying-measures.md)  
  
  