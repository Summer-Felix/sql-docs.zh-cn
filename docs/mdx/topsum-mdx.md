---
title: "TopSum (MDX) |Microsoft 文档"
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: TOPSUM
dev_langs: kbMDX
helpviewer_keywords: TopSum function
ms.assetid: e32496fd-4897-43c9-a388-4028609f4ffb
caps.latest.revision: "32"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: b6681b8cb16336c077ad4d3d6c54ab8da97c9a58
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="topsum-mdx"></a>TopSum (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  对集进行排序并返回累计合计至少达到指定值的最前面的元素。  
  
## <a name="syntax"></a>语法  
  
```  
  
TopSum(Set_Expression, Value, Numeric_Expression)   
```  
  
## <a name="arguments"></a>参数  
 *Set_Expression*  
 返回集的有效多维表达式 (MDX)。  
  
 *ReplTest1*  
 指定与每个元组相比较的值的有效数值表达式。  
  
 *Numeric_Expression*  
 返回度量值的有效数值表达式，通常是多维表达式 (MDX)。  
  
## <a name="remarks"></a>Remarks  
 **TopSum**函数计算指定的度量值，计算对指定集，以降序顺序对集进行排序的总和。 然后，该函数返回最大值元素，其指定数值表达式的合计至少为指定值。 此函数返回集的最小子集，其累积合计至少为指定值。 返回的元素按从大到小的顺序排序。  
  
> [!IMPORTANT]  
>  如[BottomSum](../mdx/bottomsum-mdx.md)函数， **TopSum**函数始终中断层次结构。  
  
## <a name="example"></a>示例  
 下面的示例返回 Geography 维度中 Geography 层次结构内 City 级别的最小成员集（对于 Bike 类别），使用 Reseller Sales Amount 度量值时该集的累积合计至少为 6,000,000（从集中具有最大销售额的成员开始）。  
  
```  
SELECT [Measures].[Reseller Sales Amount] ON 0,  
TopSum  
   ({[Geography].[Geography].[City].Members}  
   , 6000000  
   , [Measures].[Reseller Sales Amount]  
   ) ON 1  
FROM [Adventure Works]  
WHERE([Product].[Product Categories].Bikes)  
```  
  
## <a name="see-also"></a>另请参阅  
 [MDX 函数引用 &#40;MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
