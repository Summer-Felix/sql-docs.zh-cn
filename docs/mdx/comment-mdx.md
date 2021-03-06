---
title: "注释 (MDX) |Microsoft 文档"
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
f1_keywords:
- '*/'
- /*
dev_langs: kbMDX
helpviewer_keywords:
- commenting characters
- /*...*/ (comment)
ms.assetid: 64434ae4-80ce-4634-86b8-4125dfaa7f61
caps.latest.revision: "40"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 6b114c4ebdb2a8e143e7ab30cb7619b93bf5b48a
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="comment-mdx"></a>注释 (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  表示用户提供的注释文本。  
  
## <a name="syntax"></a>语法  
  
```  
  
/* Comment_Text */      
```  
  
#### <a name="parameters"></a>Parameters  
 *Comment_Text*  
 包含注释文本的字符串。  
  
## <a name="remarks"></a>Remarks  
 服务器不会评估之间注释字符的文本 / * 和\*/。 注释可以插入到单独一行中，也可以插入到多维表达式 (MDX) 语句中。 必须由指示多行注释 /\*和\*/。  
  
 注释没有最大长度限制。 注释可以嵌套，例如，`/* Test /*Comment*/ Text*/` 就是一个嵌套注释的例子。  
  
## <a name="examples"></a>示例  
 下面的示例演示了此运算符的用法。  
  
```  
/* This member returns the gross profit margin for product types  
  and reseller types crossjoined by year. */  
SELECT   
    [Date].[Calendar].[Calendar Year].Members *  
    [Reseller].[Reseller Type].Children ON 0,  
    [Product].[Category].[Category].Members ON 1  
FROM /* Select from the Adventure Works cube. */  
    [Adventure Works]  
WHERE  
    [Measures].[Gross Profit Margin]  
```  
  
## <a name="see-also"></a>另请参阅  
 [&#40;注释 &#41;&#40;MDX &#41;](../mdx/comment-mdx-double-slash.md)   
 [-&#40;注释 &#41;&#40;MDX &#41;](../mdx/comment-mdx-operator-reference.md)   
 [MDX 运算符参考 &#40;MDX &#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
