---
title: "NumericScale 属性 (ADOX) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- _Column::PutNumericScale
- _Column::GetNumericScale
- _Column::NumericScale
- _Column::put_NumericScale
- _Column::get_NumericScale
helpviewer_keywords:
- NumericScale property [ADOX]
ms.assetid: 573ee5d1-57c7-4a27-be79-a0e12944ad9b
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d24bb11f0bc8cad13b53fd418b799a40dab13f16
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="numericscale-property-adox"></a>NumericScale 属性 (ADOX)
指示列中数值的小数位数。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置并返回**字节**该键列中的数据值的刻度值时[类型](../../../ado/reference/adox-api/type-property-column-adox.md)属性是**adNumeric**或**adDecimal**。 **NumericScale**对于所有其他数据类型，将忽略。  
  
## <a name="remarks"></a>注释  
 默认值为零 (0)。  
  
 **NumericScale**是只读的[列](../../../ado/reference/adox-api/column-object-adox.md)已追加到集合的对象。  
  
## <a name="applies-to"></a>适用范围  
 [列对象 (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>另请参阅  
 [ADOX 代码示例： NumericScale 和精度属性示例 (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type 属性（列）(ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)
