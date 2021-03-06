---
title: "定义常规关系和常规关系属性 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bc2ee7a49cddc8b5d6b0ce0905e2cbcd084a8897
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a>定义常规关系和常规关系属性
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
在定义新的多维数据集维度或新的度量值组时， [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 将试图检测是否存在常规关系并将维度用法设置为 **Regular**。 您可以在多维数据集设计器的 **“维度用法”** 选项卡中查看或编辑常规维度关系。  
  
 当您定义多维数据集维度与度量值组的关系时，也会指定该关系的粒度属性。 粒度属性定义了该维度在多维数据集中可用的最低详细级别，此粒度属性通常是指维度的键属性。 但是，有时您可能希望将特定度量值组中特定多维数据集维度的粒度设置为其他粒度。 例如，如果您正在使用“销售配额”或“预算”度量值组，则可能希望将“时间”维度的粒度属性设置为“月”属性，而不是“日”属性。 当您将粒度属性指定为键属性以外的属性时，必须确保维度中的所有其他属性都能通过属性关系直接或间接地链接到该属性。 如果不能， [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 将无法正确地聚合数据。  
  
  
