---
title: "ADO Java 类包装 |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 02/15/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class wrappers [ADO]
ms.assetid: 1fc09dc1-9e32-412e-9f43-b8eb8bb483ca
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b48b4753bd7ad94b1f8b8f17a6b3c5a211dbb740
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="ado-java-class-wrappers"></a>ADO Java 类包装
此代码声明的 ADO 实例[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)类包装并初始化它，在相同的代码行上。 此外，它声明的变量中的自变量的每个[打开](../../../ado/reference/ado-api/open-method-ado-recordset.md)方法，尤其是对于[LockType](../../../ado/reference/ado-api/locktype-property-ado.md)和[游标类型](../../../ado/reference/ado-api/cursortype-property-ado.md)（因为不支持 Java 枚举类型）。 打开，并关闭**记录集**对象。 只设置为 NULL 的 Rs1 计划以 Java 执行其系统和间歇性版本的未使用的对象时释放该变量。  
  
```  
public static void main( String args[])  
{  
   msado15._Recordset   Rs1 = new msado15.Recordset();  
   Variant Source     = new Variant( "SELECT * FROM Authors" );  
   Variant Connect    = new Variant( "DSN=AdoDemo;UID=admin;PWD=;" );  
   int     LockType   = msado15.CursorTypeEnum.adOpenForwardOnly;  
   int     CursorType = msado15.LockTypeEnum.adLockReadOnly;  
   int     Options    = -1;  
  
   Rs1.Open( Source, Connect, LockType,  CursorType, Options );  
   Rs1.Close();  
   Rs1 = null;  
  
   System.out.println( "Success!\n" );  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 Java 适用的 Microsoft SDK](../../../ado/guide/appendixes/using-the-microsoft-sdk-for-java.md)
