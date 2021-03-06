---
title: "RollupChildren (MDX) |Microsoft 文档"
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
f1_keywords: ROLLUPCHILDREN
dev_langs: kbMDX
helpviewer_keywords: RollupChildren function
ms.assetid: 6f092540-067d-443f-b631-8523836a0d86
caps.latest.revision: "31"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: e3553458eecb094ec76ecb6bf7f65691aaa1c4bd
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="rollupchildren-mdx"></a>RollupChildren (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  使用指定的一元运算符，通过汇总指定成员的子成员的值，从而返回所生成的值。  
  
## <a name="syntax"></a>语法  
  
```  
  
RollupChildren(Member_Expression, Unary_Operator)   
```  
  
## <a name="arguments"></a>参数  
 *Member_Expression*  
 返回成员的有效多维表达式 (MDX)。  
  
 *Unary_Operator*  
 指定一元运算符的有效字符串表达式。  
  
## <a name="remarks"></a>Remarks  
 **RollupChildren**函数汇总使用指定的一元运算符的指定成员的子级的值。  
  
 下表说明了可用于此函数的有效一元运算符。  
  
|运算符|结果|  
|--------------|------------|  
|**+**|total = total + current child|  
|**-**|总额 = 总额 - 当前子级|  
|**\***|total = total * current child|  
|**/**|total = total / current child|  
|**%**|total = (total / current child) * 100|  
|**~**|不在汇总结果中使用子成员。 子成员的值将被忽略。|  
  
 如果成员属性中的运算符未显示在列表中，则会发生错误。 求值顺序取决于同级的顺序，而不是运算符的优先顺序。  
  
## <a name="example"></a>示例  
 下例使用名为“Alternate Rollup Operator”的成员属性（包含一元运算符的备用值）以备用方式汇总 Account（帐户）维度中 Net Profit（净利润）层次结构的子成员。 该成员属性不在 Adventure Works 多维数据集中，但是可以创建。 这种用法**RollupChildren**函数无法应用于假设分析预算方面的应用程序中使用。  
  
```  
RollupChildren  
   ( [Account].[Net Profit]  
   , [Account].CurrentMember.Properties ('Alternate Rollup Operator') )  
```  
  
## <a name="see-also"></a>另请参阅  
 [MDX 函数引用 &#40;MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
